# V. Funções customizadas

## 1. Função "jef_CONT_NUM_POR_LINHA"

```
function jef_CONT_NUM_POR_LINHA(intervalo) {
    if (!Array.isArray(intervalo)) {
        throw new Error("Dado de entrada n\xe3o \xe9 matriz.");
    }
    return intervalo.map(function (linha) {
        return linha.reduce(function (anterior, atual) {
            atual = isNaN(parseFloat(atual)) ? 0 : parseFloat(atual) > 0 ? 1 : 0;
            anterior = isNaN(parseFloat(anterior)) ? 0 : parseFloat(anterior);
            return anterior + atual;
        }, 0);
    });
}

```

## 2. Função "jef_SOMAR_LINHAS"

```
function jef_SOMAR_LINHAS(intervalo) {
    if (!Array.isArray(intervalo)) {
        throw new Error("Dado de entrada n\xe3o \xe9 matriz.");
    }
    return intervalo.map(function (linha) {
        return linha.reduce(function (anterior, atual) {
            atual = isNaN(parseFloat(atual)) ? 0 : parseFloat(atual);
            anterior = isNaN(parseFloat(anterior)) ? 0 : parseFloat(anterior);
            return anterior + atual;
        }, 0);
    });
}

```

## 3. Função "jef_EVOLUCAO_RENDA"

```
function jef_EVOLUCAO_RENDA(valorInicial, fatores) {
    if (!Array.isArray(fatores)) {
        throw new Error("Dado de entrada \"fatores\" n\xe3o \xe9 matriz.");
    }
    if (isNaN(valorInicial)) {
        throw new Error("A renda inicial informada n\xe3o \xe9 num\xe9rica.");
    }
    var valorAtual = valorInicial;
    return fatores.map(function (fator) {
        if (isNaN(fator)) {
            return valorAtual;
        }
        valorAtual *= fator;
        return valorAtual;
    });
}

```

## 4. Função "jef_JUROS_ACUMULADOS"

```
function jef_JUROS_ACUMULADOS(taxasMensais) {
    if (!Array.isArray(taxasMensais)) {
        throw new Error("Dado de entrada n\xe3o \xe9 matriz.");
    }
    return taxasMensais.map(function (taxaMensal, index, arr) {
        return arr.slice(index).reduce(function (anterior, atual) {
            if (isNaN(anterior)) {
                return atual;
            }
            if (isNaN(atual)) {
                return anterior;
            }
            return parseFloat(anterior) + parseFloat(atual);
        }, 0);
    });
}

```

## 5. Função "jef_INDICE_ACUMULADO"

```
function jef_INDICE_ACUMULADO(indices) {
    if (!Array.isArray(indices)) {
        throw new Error("Dado de entrada n\xe3o \xe9 matriz.");
    }
    return indices.map(function (indice, idx, arr) {
        return arr.slice(idx).reduce(function (anterior, atual) {
            if (isNaN(anterior) || parseFloat(anterior) === 0) {
                return atual;
            }
            if (isNaN(atual) || parseFloat(atual) === 0) {
                return anterior;
            }
            return parseFloat(anterior) * parseFloat(atual);
        }, 1);
    });
}

```
