# III. Processamento

## 1. Página "ParametrosDemonstrativos"

### 1.1. **DadosObrigatoriosFaltantes** (A44)

a) Fórmulas:
```
=IF(ISNUMBER(Protocolo);"";"Protocolo#")& IF(ISNUMBER(Citacao);"";"Citação#")&IF(ISNUMBER(DIBOriginario);"";"DIB#")&IF(ISNUMBER(RMIInformada);"";"RMI#")&IF(ISNUMBER(DataAtualizacao);"";"Data da Atualização#")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.2. **ModeloSumulaAtrasados** (D8)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.3. **ModeloSumulaBeneficio** (D2)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.4. **ObservacoesDescontos** (A23:B30)

a) Fórmulas:
```
=JOIN(CHAR(10);FILTER(OFFSET(DescontosOutrosObservacoes;6;0);OFFSET(DescontosOutrosObservacoes;6;0)<>""))
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.5. **TextoObservacoes** (A33)

a) Fórmulas:
```
=IF(MostrarObservacoesAutomaticas="Sim";IF(ISTEXT(CONCATENATE(Observacoes1));"Modificadores:"&CHAR(10)&CONCATENATE(Observacoes1)&CHAR(10)&CHAR(10);"")&IF(ISTEXT(CONCATENATE(ObservacoesDescontos));"Descontos:"&CHAR(10)&CONCATENATE(ObservacoesDescontos)&CHAR(10)&CHAR(10);"");"")&IF(ISTEXT(CONCATENATE(ObservacoesFinais));"Observações finais:"&CHAR(10)&ObservacoesFinais;"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.6. **TextoSumula** (D34)

a) Fórmulas:
```
=IF(ISTEXT(CONCATENATE(TextoSumulaOriginario));CONCATENATE(TextoSumulaOriginario)&CHAR(10);"")&IF(ISTEXT(CONCATENATE(TextoSumulaDerivado));CONCATENATE(TextoSumulaDerivado)&CHAR(10);"")&IF(ISTEXT(CONCATENATE(TextoSumulaAtrasados));CONCATENATE(TextoSumulaAtrasados);"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.7. **TextoSumulaAtrasados** (D28)

a) Fórmulas:
```
=SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(CONCATENATE(ModeloSumulaAtrasados);"${DIP}";DataFinalDiferencas+1);"${TotalAtrasados}";TotalGeral);"${DataCalculo}";DataAtualizacao);"${TotalHonorarios}";HonorariosSucumbenciaisTotal)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.8. **TextoSumulaDerivado** (D21)

a) Fórmulas:
```
=IF(ISNUMBER(DIBDerivado);"BENEFÍCIO DERIVADO:"&CHAR(10)& SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(CONCATENATE(ModeloSumulaBeneficio);"${Especie}";EspecieDerivado&" - "&INDEX(ListaBeneficios!A:B;MATCH(EspecieDerivado;ListaBeneficios!A:A;0);2);1);"${RMI}";RMIDerivado);"${RMA}";RMA);"${DIB}";DIBDerivado);"${DCB}";DCBDerivado);"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.9. **TextoSumulaOriginario** (D14)

a) Fórmulas:
```
=IF(ISNUMBER(DIBDerivado);"BENEFÍCIO ORIGINÁRIO:"&CHAR(10);"")& SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(CONCATENATE(ModeloSumulaBeneficio);"${Especie}";EspecieOriginario&" - "&INDEX(ListaBeneficios!A:B;MATCH(EspecieOriginario;ListaBeneficios!A:A;0);2);1);"${RMI}";RMIOriginario);"${RMA}";IF(ISNUMBER(DIBDerivado);"";RMA));"${DIB}";DIBOriginario);"${DCB}";DCBOriginario)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

## 2. Página "ColunasDemonstrativos"

### 2.1. **DemonstrativoAbono** (B:B)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoAbono)=1;"Linhas Abono";IF(ROW(DemonstrativoAbono)<=TotalCompetencias+1;IF(Competencia<(EOMONTH(MarcoPrescricional;-1)+1);FALSE();LinhasAbono>0);"")))
```

b) Formato:
```
0;0;-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.2. **DemonstrativoAbonoCompetencias** (N:N)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoAbonoCompetencias)=1;"Competências Abono";IF(ROW(DemonstrativoAbonoCompetencias)<=TotalCompetencias+1;IF(DemonstrativoAbono;Competencia;FALSE());"")))
```

b) Formato:
```
mm/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.3. **DemonstrativoAbonoDescontos** (Q:Q)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoAbonoDescontos)=1;"Desconto Abono";IF(ROW(DemonstrativoAbonoDescontos)<=TotalCompetencias+1;IF(DemonstrativoDiferencas;DescontoAbono;0);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00);-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.4. **DemonstrativoAbonoJuros** (T:T)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoAbonoJuros)=1;"Juros Abono";IF(ROW(DemonstrativoAbonoJuros)<=TotalCompetencias+1;IF(DemonstrativoDiferencas;JurosAbono;0);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00);-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.5. **DemonstrativoAbonoPrincipal** (R:R)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoAbonoPrincipal)=1;"Principal Abono";IF(ROW(DemonstrativoAbonoPrincipal)<=TotalCompetencias+1;IF(DemonstrativoDiferencas;PrincipalAbono;0);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00);-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.6. **DemonstrativoAbonoPrincipalAtualizado** (S:S)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoAbonoPrincipalAtualizado)=1;"Principal Abono Atualizado";IF(ROW(DemonstrativoAbonoPrincipalAtualizado)<=TotalCompetencias+1;IF(DemonstrativoDiferencas;PrincipalAbonoAtualizado;0);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00);-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.7. **DemonstrativoAbonoProporcao** (O:O)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoAbonoProporcao)=1;"Proporção Abono";IF(ROW(DemonstrativoAbonoProporcao)<=TotalCompetencias+1;IF(DemonstrativoAbono;IF(ProporcaoAbono=1;"Integral";ProporcaoAbono);0);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00);-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.8. **DemonstrativoAbonoTotal** (U:U)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoAbonoTotal)=1;"Total Abono";IF(ROW(DemonstrativoAbonoTotal)<=TotalCompetencias+1;IF(DemonstrativoDiferencas;TotalAbono;0);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00);-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.9. **DemonstrativoAbonoValor** (P:P)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoAbonoValor)=1;"Valor Abono";IF(ROW(DemonstrativoAbonoValor)<=TotalCompetencias+1;IF(DemonstrativoDiferencas;Abono;0);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00);-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.10. **DemonstrativoDiferencas** (C:C)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoDiferencas)=1;"Linhas Diferenças";IF(ROW(DemonstrativoDiferencas)<=TotalCompetencias+1;IF(Competencia<(EOMONTH(MarcoPrescricional;-1)+1);FALSE();TRUE());"")))
```

b) Formato:
```
#,##0.00;(#,##0.00);-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.11. **DemonstrativoFatorAtualizacao** (I:I)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoFatorAtualizacao)=1;"Fator Atualização";IF(ROW(DemonstrativoFatorAtualizacao)<=TotalCompetencias+1;IF(DemonstrativoDiferencas;FatorAtualizacao;0);"")))
```

b) Formato:
```
#,##0.0000000000;(#,##0.0000000000);-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.12. **DemonstrativoFatorReajuste** (E:E)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoFatorReajuste)=1;"Reajuste";IF(ROW(DemonstrativoFatorReajuste)<=TotalCompetencias+1;IF(DemonstrativoRenda;IF(FatorReajuste<>1;FatorReajuste;0));"")))
```

b) Formato:
```
#,##0.0000000000;(#,##0.0000000000)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.13. **DemonstrativoJurosPercentual** (K:K)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoJurosPercentual)=1;"Percentual Juros de Mora";IF(ROW(DemonstrativoJurosPercentual)<=TotalCompetencias+1;IF(DemonstrativoDiferencas;JurosAcumulados;0);"")))
```

b) Formato:
```
0.00%
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.14. **DemonstrativoRenda** (A:A)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoRenda)=1;"Linhas Renda";IF(ROW(DemonstrativoRenda)<=TotalCompetencias+1;IF(ROW(DemonstrativoRenda)=2;TRUE();IF(ISNUMBER(RendaAtualArt58);IF(Competencia=DATE(1991;12;1);TRUE();IF(Competencia<DATE(1992;1;1);FALSE();IF(Competencia<(EOMONTH(MarcoPrescricional;-1)+1);Reajustar;TRUE())));IF(Competencia<(EOMONTH(MarcoPrescricional;-1)+1);Reajustar;TRUE())));"")))
```

b) Formato:
```
#,##0.0000000000;(#,##0.0000000000)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.15. **DemonstrativoRendaCompetencias** (D:D)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoRendaCompetencias)=1;"Competências Renda";IF(ROW(DemonstrativoRendaCompetencias)<=TotalCompetencias+1;IF(DemonstrativoRenda;Competencia;FALSE());"")))
```

b) Formato:
```
mm/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.16. **DemonstrativoRendaDescontos** (G:G)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoRendaDescontos)=1;"Desconto Renda";IF(ROW(DemonstrativoRendaDescontos)<=TotalCompetencias+1;IF(DemonstrativoDiferencas;DescontoRenda;0);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00);-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.17. **DemonstrativoRendaJuros** (L:L)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoRendaJuros)=1;"Juros Renda";IF(ROW(DemonstrativoRendaJuros)<=TotalCompetencias+1;IF(DemonstrativoDiferencas;JurosRenda;0);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00);-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.18. **DemonstrativoRendaMensal** (F:F)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoRendaMensal)=1;"Renda Mensal";IF(ROW(DemonstrativoRendaMensal)<=TotalCompetencias+1;IF(DemonstrativoRenda;RendaMensalEfetiva;0);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00);-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.19. **DemonstrativoRendaPrincipal** (H:H)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoRendaPrincipal)=1;"Principal Renda";IF(ROW(DemonstrativoRendaPrincipal)<=TotalCompetencias+1;IF(DemonstrativoDiferencas;PrincipalRenda;0);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00);-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.20. **DemonstrativoRendaPrincipalAtualizado** (J:J)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoRendaPrincipalAtualizado)=1;"Principal Renda Atualizado";IF(ROW(DemonstrativoRendaPrincipalAtualizado)<=TotalCompetencias+1;IF(DemonstrativoDiferencas;PrincipalRendaAtualizado;0);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00);-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.21. **DemonstrativoRendaTotal** (M:M)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoRendaTotal)=1;"Total Renda";IF(ROW(DemonstrativoRendaTotal)<=TotalCompetencias+1;IF(DemonstrativoDiferencas;TotalRenda;0);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.22. **DemonstrativoTotalMes** (V:V)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DemonstrativoTotalMes)=1;"Total Mês";IF(ROW(DemonstrativoTotalMes)<=TotalCompetencias+1;IF(DemonstrativoDiferencas;TotalMes;0);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00);-
```

c) Regras de validação: não há  
d) Notas: não há  
