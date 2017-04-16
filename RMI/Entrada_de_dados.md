# II. Entrada de Dados

## 1. Página "Processo"

### 1.1. **AtividadeSecundaria** (D16)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_LIST Não,Sim
```

d) Notas: não há  

### 1.2. **Autor** (D6)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.3. **BeneficioDeficiente** (K9)

a) Fórmulas: não há  
b) Formato:
```
#,##0
```

c) Regras de validação:
```VALUE_IN_LIST Sim,Não
```

d) Notas: não há  

### 1.4. **Citacao** (D9)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.5. **Coeficiente** (K8)

a) Fórmulas: não há  
b) Formato:
```
0.00%
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.6. **DIB** (K7)

a) Fórmulas: não há  
b) Formato: padrão  
c) Regras de validação:
```DATE_IS_VALID_DATE 
```

d) Notas: não há  

### 1.7. **DataNascimento** (D13)

a) Fórmulas: não há  
b) Formato:
```
dd/mm/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.8. **DenominadorAtividadeSecundaria** (D18)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.9. **Especie** (K6)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_RANGE ListaBeneficios!A:A
```

d) Notas: não há  

### 1.10. **NB** (K5)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.11. **NumeradorAtividadeSecundaria** (D17)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.12. **Processo** (D5)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.13. **Protocolo** (D8)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.14. **Reu** (D7)

a) Fórmulas: não há  
b) Formato:
```
#,##0
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.15. **Sexo** (D12)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_LIST Homem,Mulher
```

d) Notas: não há  

### 1.16. **TCAnos** (K12)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```NUMBER_GREATER_THAN_OR_EQUAL_TO 0
```

d) Notas: não há  

### 1.17. **TCDias** (K14)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```NUMBER_GREATER_THAN_OR_EQUAL_TO 0
```

d) Notas: não há  

### 1.18. **TCMeses** (K13)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```NUMBER_GREATER_THAN_OR_EQUAL_TO 0
```

d) Notas: não há  

## 2. Página "Modificadores1"

### 2.1. **AplicarFatorPrevidenciario** (D18)

a) Fórmulas:
```
=IF(AND(AplicarFatorPrevidenciarioModificado<>"PADRÃO";AplicarFatorPrevidenciarioModificado<>"");AplicarFatorPrevidenciarioModificado;IF(AND(MID(Especie;1;2)="42";OR(BeneficioDeficiente="Sim"; AND(ISNUMBER(PontuacaoMinima);Pontos>=PontuacaoMinima;TCTotalAnos>=TCMinimoPontuacao)));"FACULTATIVO";INDEX(ListaBeneficios!A:E;MATCH(Especie;ListaBeneficios!A:A;0);5)))
```

b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.2. **AplicarFatorPrevidenciarioModificado** (F18)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_RANGE ListaBeneficios!E:E
```

d) Notas: não há  

### 2.3. **ApurarIndiceTetoComFatorPrevidenciario** (D20)

a) Fórmulas:
```
=IF(AND(ApurarIndiceTetoComFatorPrevidenciarioModificado<>"PADRÃO";ApurarIndiceTetoComFatorPrevidenciarioModificado<>"");ApurarIndiceTetoComFatorPrevidenciarioModificado;"SIM")
```

b) Formato:
```
#,##0.00;(#,##0.00)
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.4. **ApurarIndiceTetoComFatorPrevidenciarioModificado** (F20)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_LIST SIM,NÃO
```

d) Notas: não há  

### 2.5. **CriterioPC** (D17)

a) Fórmulas:
```
=IF(AND(MID(CriterioPCModificado;1;1)<>"0";CriterioPCModificado<>"");CriterioPCModificado;INDEX(OpcoesPC!A:A;INDEX(ListaBeneficios!A:E;MATCH(Especie;ListaBeneficios!A:A;0);IF(DDA<DPL;3;4))+1))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 2.6. **CriterioPCModificado** (F17)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_RANGE OpcoesPC!A:A
```

d) Notas: não há  

### 2.7. **DDA** (D14)

a) Fórmulas:
```
=IF(ISNUMBER(DDAModificada);DDAModificada;DIB)
```

b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.8. **DDAModificada** (F14)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.9. **DPL** (D7)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.10. **DataInicioVigenciaPontos** (D8)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.11. **ExpectativaSobrevida** (D16)

a) Fórmulas:
```
=IF(ISNUMBER(ExpectativaSobrevidaModificada);ExpectativaSobrevidaModificada;INDEX(TabuasMortalidade!A:CD;MATCH(TabuaMortalidadeUtilizada;TabuasMortalidade!A:A;0);MATCH(Idade;TabuasMortalidade!1:1;0)))
```

b) Formato:
```
#,##0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.12. **ExpectativaSobrevidaModificada** (F16)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.13. **Idade** (D6)

a) Fórmulas:
```
=DATEDIF(DataNascimento;DIB;"Y")
```

b) Formato:
```
#,##0;(#,##0)
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.14. **Limitacao12Ultimos** (D19)

a) Fórmulas:
```
=IF(AND(Limitacao12UltimosModificada<>"PADRÃO";Limitacao12UltimosModificada<>"");Limitacao12UltimosModificada;IF(DDA<DATEVALUE("2015-03-01");"NÃO";INDEX(ListaBeneficios!A:F;MATCH(Especie;ListaBeneficios!A:A;0);6)))
```

b) Formato:
```
#,##0.00;(#,##0.00)
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.15. **Limitacao12UltimosModificada** (F19)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_RANGE ListaBeneficios!F:F
```

d) Notas: não há  

### 2.16. **Pontos** (D13)

a) Fórmulas:
```
=IF(ISNUMBER(PontosModificados);PontosModificados;IF(AND(ISNUMBER(TCAnos);ISNUMBER(TCMeses);ISNUMBER(TCDias);ISNUMBER(DataNascimento));TCAnos+(TCMeses/12)+(TCDias/360)+Idade;0))
```

b) Formato:
```
#,##0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.17. **PontosModificados** (F13)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.18. **PontuacaoMinima** (D10)

a) Fórmulas:
```
=IF(DDA<DataInicioVigenciaPontos;"não se aplica";INDEX(TabelaPontuacao!A:C;MATCH(DDA;TabelaPontuacao!A:A;1);IF(Sexo="Homem";2;3)))
```

b) Formato:
```
#,##0.00;(#,##0.00)
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.19. **SalarioBeneficioModificado** (E9)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.20. **TCMinimo** (D11)

a) Fórmulas:
```
=IF(Sexo="Homem";35;30)
```

b) Formato:
```
#,##0.00;(#,##0.00)
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.21. **TCMinimoPontuacao** (D11)

a) Fórmulas:
```
=IF(Sexo="Homem";35;30)
```

b) Formato:
```
#,##0.00;(#,##0.00)
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.22. **TCTotalAnos** (D9)

a) Fórmulas:
```
=IF(AND(ISNUMBER(TCAnos);ISNUMBER(TCMeses);ISNUMBER(TCDias);ISNUMBER(DataNascimento));TCAnos+(TCMeses/12)+(TCDias/360);0)
```

b) Formato:
```
#,##0.00;(#,##0.00)
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.23. **TabuaMortalidadeUtilizada** (D15)

a) Fórmulas:
```
=IF(ISNUMBER(TabuaMortalidadeUtilizadaModificada);TabuaMortalidadeUtilizadaModificada;MIN(YEAR(DDA)-2;UltimaTabuaMortalidade))
```

b) Formato:
```
###0
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.24. **TabuaMortalidadeUtilizadaModificada** (F15)

a) Fórmulas: não há  
b) Formato:
```
###0
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.25. **UltimaTabuaMortalidade** (D12)

a) Fórmulas:
```
=MAX(TabuasMortalidade!A:A)
```

b) Formato:
```
###0
```

c) Regras de validação: não há  
d) Notas: não há  

## 3. Página "Modificadores2"

### 3.1. **CompetenciaModificadores** (C:C)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(CompetenciaIndices)=1;"Competência";CompetenciaIndices))
```

b) Formato:
```
mm/yyyy
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.2. **ModificadoresIndiceMensalAtualizacao** (F:F)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00000000;(#,##0.00000000)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.3. **ModificadoresObservacoes** (I:I)

a) Fórmulas: não há  
b) Formato:
```
0.00%
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.4. **ModificadoresPiso** (D:D)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.5. **ModificadoresSalarios** (G:G)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.6. **ModificadoresTeto** (E:E)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.7. **ModificadoresUsarPiso** (H:H)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

## 4. Página "Salarios"

### 4.1. **MarcoFinalAplicacaoArt32** (A4)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.2. **SalariosContribuicao** (D:D)

a) Fórmulas: não há  
b) Formato:
```
0.###############
dd/MM/yyyy
#,##0.00
#,##0.00;(#,##0.00)
```

c) Regras de validação:
```VALUE_IN_RANGE OpcoesAtividadesConcomitantes!A:A
```

d) Notas: não há  

### 4.3. **ValorAtividadeSecundaria** (A2)

a) Fórmulas: não há  
b) Formato:
```
#,##0.00_);[Red](#,##0.00)
```

c) Regras de validação: não há  
d) Notas: não há  
