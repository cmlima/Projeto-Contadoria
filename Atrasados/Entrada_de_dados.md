# II. Entrada de Dados

## 1. Página "Processo"

### 1.1. **Autor** (D6)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.2. **Citacao** (D9)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.3. **CriterioAlcada** (D15)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_RANGE OpcoesAlcada!A:A
```

d) Notas: não há  

### 1.4. **DER** (D10)

a) Fórmulas: não há  
b) Formato:
```
dd/mm/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.5. **NaturezaAcao** (D11)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_RANGE OpcoesAcao!A:A
```

d) Notas: não há  

### 1.6. **Processo** (D5)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.7. **Protocolo** (D8)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.8. **Reu** (D7)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

## 2. Página "Atualizacao"

### 2.1. **CriterioCorrecao** (D9)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_RANGE OpcoesCorrecao!A:A
```

d) Notas: não há  

### 2.2. **CriterioJuros** (D10)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_RANGE OpcoesJuros!A:A
```

d) Notas: não há  

### 2.3. **CriterioReajuste** (D5)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_RANGE OpcoesReajuste!A:A
```

d) Notas: não há  

### 2.4. **DataAtualizacao** (D11)

a) Fórmulas: não há  
b) Formato:
```
d/m/yyyy
```

c) Regras de validação:
```DATE_IS_VALID_DATE 
```

d) Notas: não há  

### 2.5. **HonorariosContratuaisBaseJuros** (I14)

a) Fórmulas:
```
=IF(ISNUMBER(HonorariosContratuaisBaseJurosModificada);HonorariosContratuaisBaseJurosModificada;SUMIFS(TotalJuros;Competencia;"<"&EOMONTH(HonorariosContratuaisDataApuracao;-1)+1))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.6. **HonorariosContratuaisBaseJurosModificada** (J14)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.7. **HonorariosContratuaisBasePrincipal** (I13)

a) Fórmulas:
```
=IF(ISNUMBER(HonorariosContratuaisBasePrincipalModificada);HonorariosContratuaisBasePrincipalModificada;SUMIFS(PrincipalTotalAtualizado;Competencia;"<"&EOMONTH(HonorariosContratuaisDataApuracao;-1)+1))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.8. **HonorariosContratuaisBasePrincipalModificada** (J13)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.9. **HonorariosContratuaisDataApuracao** (I12)

a) Fórmulas:
```
=IF(ISNUMBER(HonorariosContratuaisDataApuracaoModificada);HonorariosContratuaisDataApuracaoModificada;DataAtualizacao)
```

b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.10. **HonorariosContratuaisDataApuracaoModificada** (J12)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação:
```DATE_IS_VALID_DATE 
```

d) Notas: não há  

### 2.11. **HonorariosContratuaisLimite** (I15)

a) Fórmulas:
```
=IF(ISNUMBER(HonorariosContratuaisLimiteModificado);HonorariosContratuaisLimiteModificado;0)
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.12. **HonorariosContratuaisLimiteModificado** (J15)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.13. **HonorariosContratuaisPercentual** (I11)

a) Fórmulas:
```
=IF(ISNUMBER(HonorariosContratuaisPercentualModificado);HonorariosContratuaisPercentualModificado;0)
```

b) Formato:
```
0.00%;(0.00%)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.14. **HonorariosContratuaisPercentualModificado** (J11)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.15. **HonorariosSucumbenciaisBaseIncidencia** (I7)

a) Fórmulas:
```
=IF(ISNUMBER(HonorariosSucumbenciaisBaseIncidenciaModificada);HonorariosSucumbenciaisBaseIncidenciaModificada;SUMIFS(TotalMes;Competencia;"<"&EOMONTH(HonorariosSucumbenciaisDataApuracao;-1)+1))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.16. **HonorariosSucumbenciaisBaseIncidenciaModificada** (J7)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.17. **HonorariosSucumbenciaisDataApuracao** (I6)

a) Fórmulas:
```
=IF(ISNUMBER(HonorariosSucumbenciaisDataApuracaoModificada);HonorariosSucumbenciaisDataApuracaoModificada;DataAtualizacao)
```

b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.18. **HonorariosSucumbenciaisDataApuracaoModificada** (J6)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação:
```DATE_IS_VALID_DATE 
```

d) Notas: não há  

### 2.19. **HonorariosSucumbenciaisLimite** (I8)

a) Fórmulas:
```
=IF(ISNUMBER(HonorariosLimiteModificado);HonorariosLimiteModificado;0)
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.20. **HonorariosSucumbenciaisLimiteModificado** (J8)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.21. **HonorariosSucumbenciaisPercentual** (I5)

a) Fórmulas:
```
=IF(ISNUMBER(HonorariosSucumbenciaisPercentualModificado);HonorariosSucumbenciaisPercentualModificado;0)
```

b) Formato:
```
0.00%;(0.00%)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.22. **HonorariosSucumbenciaisPercentualModificado** (J5)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.23. **IndiceTeto** (D6)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

## 3. Página "Descontos"

### 3.1. **CompetenciaDescontos** (C:C)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(CompetenciaIndices)=1;"Competência";CompetenciaIndices))
```

b) Formato:
```
mm/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.2. **DescontosBeneficioPagoAbono** (E:E)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(CompetenciaIndices)=1;"Abono";IF(ROW(CompetenciaIndices)<MATCH(CompetenciaInicial;CompetenciaIndices;0);0;IF(ROW(CompetenciaIndices)>MATCH(CompetenciaFinal;CompetenciaIndices;0);0;IF(MID(NaturezaAcao;1;1)="2";IFERROR(VLOOKUP(OFFSET(CompetenciaDescontos;4;0);OFFSET(Competencia;0;0;ROWS(Competencia);COLUMN(AbonoNBPago));COLUMN(AbonoNBPago);TRUE);0);0)))))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.3. **DescontosBeneficioPagoRenda** (D:D)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(CompetenciaIndices)=1;"Abono";IF(ROW(CompetenciaIndices)<MATCH(CompetenciaInicial;CompetenciaIndices;0);0;IF(ROW(CompetenciaIndices)>MATCH(CompetenciaFinal;CompetenciaIndices;0);0;IF(MID(NaturezaAcao;1;1)="2";IFERROR(VLOOKUP(OFFSET(CompetenciaDescontos;4;0);OFFSET(Competencia;0;0;ROWS(Competencia);COLUMN(ValorQuotaNBPago));COLUMN(ValorQuotaNBPago);TRUE);0);0)))))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.4. **DescontosConsignacao** (G:G)

a) Fórmulas: não há  
b) Formato:
```
0.00%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.5. **DescontosNB1** (M4)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.6. **DescontosNB1Abono** (N:N)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.7. **DescontosNB1Renda** (M:M)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.8. **DescontosNB2** (O4)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.9. **DescontosNB2Abono** (P:P)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.10. **DescontosNB2Renda** (O:O)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.11. **DescontosNB3** (Q4)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.12. **DescontosNB3Abono** (R:R)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.13. **DescontosNB3Renda** (Q:Q)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.14. **DescontosNB4** (S4)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.15. **DescontosNB4Abono** (T:T)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.16. **DescontosNB4Renda** (S:S)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.17. **DescontosNB5** (U4)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.18. **DescontosNB5Abono** (V:V)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.19. **DescontosNB5Renda** (U:U)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.20. **DescontosOutrosAbonoPercentual** (J:J)

a) Fórmulas: não há  
b) Formato:
```
0.00%
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.21. **DescontosOutrosAbonoValor** (K:K)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.22. **DescontosOutrosObservacoes** (L:L)

a) Fórmulas: não há  
b) Formato:
```
0.00%;(0.00%)[Red];-
0.###############
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.23. **DescontosOutrosRendaPercentual** (H:H)

a) Fórmulas: não há  
b) Formato:
```
0.00%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.24. **DescontosOutrosRendaValor** (I:I)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.25. **DescontosRendaExcluida** (F:F)

a) Fórmulas: não há  
b) Formato:
```
0.00%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.26. **DescontosTotalAbonoPercentual** (Z:Z)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(CompetenciaIndices)=1;"Perc. Abono";OFFSET(DescontosOutrosAbonoPercentual;4;0;ROWS(CompetenciaIndices))+0))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.27. **DescontosTotalAbonoValor** (X:X)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(CompetenciaIndices)=1;"Valor Abono";OFFSET(DescontosNB1Abono;4;0;ROWS(CompetenciaIndices))+OFFSET(DescontosNB2Abono;4;0;ROWS(CompetenciaIndices))+OFFSET(DescontosNB3Abono;4;0;ROWS(CompetenciaIndices))+OFFSET(DescontosNB4Abono;4;0;ROWS(CompetenciaIndices))+OFFSET(DescontosNB5Abono;4;0;ROWS(CompetenciaIndices))+OFFSET(DescontosBeneficioPagoAbono;4;0;ROWS(CompetenciaIndices))+OFFSET(DescontosOutrosAbonoValor;4;0;ROWS(CompetenciaIndices))))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.28. **DescontosTotalRendaPercentual** (Y:Y)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(CompetenciaIndices)=1;"Perc. Renda";OFFSET(DescontosRendaExcluida;4;0;ROWS(CompetenciaIndices))+OFFSET(DescontosConsignacao;4;0;ROWS(CompetenciaIndices))+OFFSET(DescontosOutrosRendaPercentual;4;0;ROWS(CompetenciaIndices))))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.29. **DescontosTotalRendaValor** (W:W)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(CompetenciaIndices)=1;"Valor Renda";OFFSET(DescontosNB1Renda;4;0;ROWS(CompetenciaIndices))+OFFSET(DescontosNB2Renda;4;0;ROWS(CompetenciaIndices))+OFFSET(DescontosNB3Renda;4;0;ROWS(CompetenciaIndices))+OFFSET(DescontosNB4Renda;4;0;ROWS(CompetenciaIndices))+OFFSET(DescontosNB5Renda;4;0;ROWS(CompetenciaIndices))+OFFSET(DescontosBeneficioPagoRenda;4;0;ROWS(CompetenciaIndices))+OFFSET(DescontosOutrosRendaValor;4;0;ROWS(CompetenciaIndices))))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  
