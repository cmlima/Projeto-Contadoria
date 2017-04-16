# V. Funções customizadas

## 1. Função "jef_CALCULAR_ACRESCIMOS_LEI_11718"

```
function jef_CALCULAR_ACRESCIMOS_LEI_11718(periodos, aplicacaoRetroativa) {
    periodos = Utilidades.validarPeriodos(periodos);
    var multiplicador = function (ano) {
        if (ano <= 2010) {
            return aplicacaoRetroativa ? 2 : 0;
        } else {
            if (ano <= 2015) {
                return 2;
            } else {
                if (ano <= 2020) {
                    return 1;
                } else {
                    return 0;
                }
            }
        }
    };
    var contribuicoes = Object.create(null);
    periodos.forEach(function (periodo) {
        var anoInicial = Utilidades.ano(periodo[0]);
        var mesInicial = Utilidades.mes(periodo[0]);
        var anoFinal = Utilidades.ano(periodo[1]);
        var mesFinal = Utilidades.mes(periodo[1]);
        contribuicoes[anoInicial] = contribuicoes[anoInicial] || [];
        contribuicoes[anoFinal] = contribuicoes[anoFinal] || [];
        if (anoInicial === anoFinal) {
            for (var i = mesInicial; i <= mesFinal; i++) {
                contribuicoes[anoInicial].push(i);
            }
        } else {
            for (var i = mesInicial; i <= 12; i++) {
                contribuicoes[anoInicial].push(i);
            }
            for (var i = 1; i <= mesFinal; i++) {
                contribuicoes[anoFinal].push(i);
            }
        }
    });
    Object.keys(contribuicoes).forEach(function (key) {
        var arr = [];
        for (var i = 0, l = contribuicoes[key].length; i < l; i++) {
            if (arr.indexOf(contribuicoes[key][i]) < 0) {
                arr.push(contribuicoes[key][i]);
            }
        }
        contribuicoes[key] = arr;
    });
    var acrescimos = periodos.map(function (periodo, idx) {
        var anoInicial = Utilidades.ano(periodo[0]);
        var mesInicial = Utilidades.mes(periodo[0]);
        var anoFinal = Utilidades.ano(periodo[1]);
        var mesFinal = Utilidades.mes(periodo[1]);
        if (idx > 0 && anoInicial === Utilidades.ano(periodos[idx - 1][1]) && mesInicial === Utilidades.mes(periodos[idx - 1][1])) {
            var ajuste = -1;
        } else {
            var ajuste = 0;
        }
        if (anoInicial === anoFinal) {
            var acrescimoInicial = (mesFinal - mesInicial + 1 + ajuste) * multiplicador(anoInicial);
            var acrescimoFinal = 0;
            var disponivelInicial = 12 - contribuicoes[anoInicial].length;
            var acrescimoInicial = Math.min(acrescimoInicial, disponivelInicial);
            if (acrescimoInicial > 0) {
                for (var i = 1; i <= acrescimoInicial; i++) {
                    contribuicoes[anoInicial].push(1);
                }
            }
        } else {
            var acrescimoInicial = (12 - mesInicial + 1 + ajuste) * multiplicador(anoInicial);
            var disponivelInicial = 12 - contribuicoes[anoInicial].length;
            var acrescimoInicial = Math.min(acrescimoInicial, disponivelInicial);
            if (acrescimoInicial > 0) {
                for (var i = 1; i <= acrescimoInicial; i++) {
                    contribuicoes[anoInicial].push(1);
                }
            }
            var acrescimoFinal = mesFinal * multiplicador(anoFinal);
            var disponivelFinal = 12 - contribuicoes[anoFinal].length;
            var acrescimoFinal = Math.min(acrescimoFinal, disponivelFinal);
            if (acrescimoFinal > 0) {
                for (var i = 1; i <= acrescimoFinal; i++) {
                    contribuicoes[anoFinal].push(1);
                }
            }
        }
        return Math.max(acrescimoInicial + acrescimoFinal, 0);
    });
    return acrescimos;
}

```

## 2. Função "jef_ELIMINAR_CONCOMITANCIA"

```
function jef_ELIMINAR_CONCOMITANCIA(periodos) {
    periodos = Utilidades.validarPeriodos(periodos);
    if (periodos.length === 1) {
        return periodos;
    }
    periodos = periodos.sort(Utilidades.ordenarPorDataInicial);
    var contador = 0;
    do {
        var acrescimos = [];
        var conflitoDetectado = false;
        var maxIdx = periodos.length - 1;
        contador += 1;
        for (var i = 0; i < maxIdx; i++) {
            if (periodos[i] && periodos[i + 1]) {
                var dataInicialPrimeiro = new Date(periodos[i][0].getTime());
                var dataFinalPrimeiro = new Date(periodos[i][1].getTime());
                var pesoPrimeiro = periodos[i][periodos[i].length - 1];
                var dataInicialSegundo = new Date(periodos[i + 1][0].getTime());
                var dataFinalSegundo = new Date(periodos[i + 1][1].getTime());
                var pesoSegundo = periodos[i + 1][periodos[i + 1].length - 1];
                var conflito = Utilidades.datasSobrepostas(dataInicialPrimeiro, dataFinalPrimeiro, dataInicialSegundo, dataFinalSegundo);
                if (conflito) {
                    if (pesoPrimeiro >= pesoSegundo) {
                        if (dataFinalSegundo > dataFinalPrimeiro) {
                            periodos[i + 1][0] = Utilidades.diaSeguinte(dataFinalPrimeiro);
                        } else {
                            periodos[i + 1] = null;
                        }
                    } else {
                        if (dataInicialPrimeiro === dataInicialSegundo && dataFinalPrimeiro <= dataFinalSegundo) {
                            periodos[i] = null;
                        } else {
                            if (dataInicialPrimeiro < dataInicialSegundo) {
                                periodos[i][1] = Utilidades.diaAnterior(dataInicialSegundo);
                            }
                            if (dataFinalPrimeiro > dataFinalSegundo) {
                                acrescimos.push(Utilidades.copiarMatriz(periodos[i]));
                                acrescimos[acrescimos.length - 1][0] = Utilidades.diaSeguinte(dataFinalSegundo);
                                acrescimos[acrescimos.length - 1][1] = dataFinalPrimeiro;
                            }
                        }
                    }
                }
                conflitoDetectado = conflitoDetectado || conflito;
            }
        }
        if (conflitoDetectado && acrescimos.length > 0) {
            acrescimos.forEach(function (acrescimo) {
                periodos.push(acrescimo);
            });
        }
        periodos = periodos.filter(Utilidades.compactarMatriz).sort(Utilidades.ordenarPorDataInicial);
        if (contador > 1000) {
            throw new Error("Falha no programa. Loop infinito.");
        }
    } while (acrescimos.length > 0 || conflitoDetectado);
    return periodos;
}

```

## 3. Função "jef_ESTABELECER_MARCOS_TEMPORAIS"

```
function jef_ESTABELECER_MARCOS_TEMPORAIS(periodos, marcosTemporais) {
    marcosTemporais = Utilidades.validarMarcosTemporais(marcosTemporais);
    if (marcosTemporais.length === 0) {
        return periodos;
    }
    periodos = Utilidades.validarPeriodos(periodos);
    periodos = periodos.sort(Utilidades.ordenarPorDataInicial);
    var contador = 0;
    do {
        var acrescimos = [];
        contador += 1;
        periodos.forEach(function (periodo) {
            marcosTemporais.forEach(function (marcoTemporal) {
                if (Utilidades.incluiMarcoTemporal(periodo[0], periodo[1], marcoTemporal)) {
                    var novoPeriodo = Utilidades.copiarMatriz(periodo);
                    periodo[1] = Utilidades.diaAnterior(marcoTemporal);
                    novoPeriodo[0] = marcoTemporal;
                    acrescimos.push(novoPeriodo);
                }
            });
        });
        if (acrescimos.length > 0) {
            acrescimos.forEach(function (acrescimo) {
                periodos.push(acrescimo);
            });
        }
        periodos = periodos.sort(Utilidades.ordenarPorDataInicial);
        if (contador > 1000) {
            throw new Error("Falha no programa. Loop infinito.");
        }
    } while (acrescimos.length > 0);
    return periodos.sort(Utilidades.ordenarPorDataInicial);
}

```

## 4. Função "Utilidades.datasSobrepostas"

```
function (inicialPrimeiro, finalPrimeiro, inicialSegundo, finalSegundo) {
    return (inicialPrimeiro <= finalSegundo) && (finalPrimeiro >= inicialSegundo);
}

```

## 5. Função "Utilidades.incluiMarcoTemporal"

```
function (dataInicial, dataFinal, marco) {
    return marco > dataInicial && marco <= dataFinal;
}

```

## 6. Função "Utilidades.ordenarPorDataInicial"

```
function (linha1, linha2) {
    return linha1[0] - linha2[0];
}

```

## 7. Função "Utilidades.compactarMatriz"

```
function (linha) {
    return linha !== null;
}

```

## 8. Função "Utilidades.isDate"

```
function (elem) {
    return Object.prototype.toString.call(elem).slice(8, -1) === "Date";
}

```

## 9. Função "Utilidades.diaSeguinte"

```
function (d) {
    var novaData = new Date(d.getTime());
    novaData.setDate(d.getDate() + 1);
    return novaData;
}

```

## 10. Função "Utilidades.diaAnterior"

```
function (d) {
    var novaData = new Date(d.getTime());
    novaData.setDate(d.getDate() - 1);
    return novaData;
}

```

## 11. Função "Utilidades.ano"

```
function (d) {
    return parseInt(Utilities.formatDate(d, "UTC", "yyyy"), 10);
}

```

## 12. Função "Utilidades.mes"

```
function (d) {
    return parseInt(Utilities.formatDate(d, "UTC", "MM"), 10);
}

```

## 13. Função "Utilidades.copiarMatriz"

```
function (arr) {
    return arr.map(function (item) {
        return item;
    });
}

```

## 14. Função "Utilidades.validarPeriodos"

```
function (periodos) {
    if (!Array.isArray(periodos)) {
        throw new Error("Dado de entrada \"periodos\" n\xe3o \xe9 matriz.");
    }
    periodos = periodos.filter(function (periodo) {
        return periodo[0] !== "" && periodo[1] !== "";
    });
    periodos.forEach(function (periodo, idx) {
        if (!utils.isDate(periodo[0]) || !utils.isDate(periodo[1])) {
            throw new Error("A linha " + (idx + 1) + " da matriz fornecida cont\xe9m uma data inv\xe1lida.");
        }
        if (periodo[0] > periodo[1]) {
            throw new Error("Na linha " + (idx + 1) + " da matriz fornecida a data inicial \xe9 maior que a final.");
        }
    });
    return periodos;
}

```

## 15. Função "Utilidades.validarMarcosTemporais"

```
function (marcosTemporais) {
    if (!Array.isArray(marcosTemporais)) {
        throw new Error("Dado de entrada \"marcosTemporais\" n\xe3o \xe9 matriz.");
    }
    marcosTemporais = marcosTemporais.map(function (linha) {
        return linha[0];
    }).filter(function (marcoTemporal) {
        return utils.isDate(marcoTemporal);
    }).sort(function (data1, data2) {
        return data1 - data2;
    });
    return marcosTemporais;
}

```
