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

### 1.2. **BeneficioDeficiente** (K9)

a) Fórmulas: não há  
b) Formato:
```
#,##0
```

c) Regras de validação:
```VALUE_IN_LIST Sim,Não
```

d) Notas: não há  

### 1.3. **BeneficioRural** (K8)

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

### 1.5. **DER** (K7)

a) Fórmulas: não há  
b) Formato: padrão  
c) Regras de validação:
```DATE_IS_VALID_DATE 
```

d) Notas: não há  

### 1.6. **DataNascimento** (D13)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.7. **Especie** (K6)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_RANGE ListaBeneficios!A:A
```

d) Notas: não há  

### 1.8. **NB** (K5)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.9. **Processo** (D5)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.10. **Protocolo** (D8)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.11. **Reu** (D7)

a) Fórmulas: não há  
b) Formato:
```
#,##0
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.12. **Sexo** (D12)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_LIST Homem,Mulher
```

d) Notas: não há  

### 1.13. **TCAposentadoriaIntegral** (K12)

a) Fórmulas:
```
=IF(ISNUMBER(TCAposentadoriaIntegralModificado);TCAposentadoriaIntegralModificado;IF(Especie=42;IF(Sexo="Homem";35;30)))
```

b) Formato:
```
#,##0
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.14. **TCAposentadoriaIntegralModificado** (L12)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

## 2. Página "ConfigurarContagem"

### 2.1. **AjustarMarcosTemporais** (H6)

a) Fórmulas: não há  
b) Formato:
```
#,##0
```

c) Regras de validação:
```VALUE_IN_LIST Sim,Não
```

d) Notas: não há  

### 2.2. **AplicarLei11718** (H7)

a) Fórmulas: não há  
b) Formato:
```
#,##0
```

c) Regras de validação:
```VALUE_IN_LIST 1 - Não,2 - A partir de sua vigência,3 - Retroativamente
```

d) Notas: não há  

### 2.3. **DERReafirmada1** (H11)

a) Fórmulas:
```
=Protocolo
```

b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.4. **DERReafirmada2** (H12)

a) Fórmulas:
```
=Citacao
```

b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.5. **DLB** (D6)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.6. **DPEMaisUm** (D7)

a) Fórmulas:
```
=DPE+1
```

b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.7. **DPL** (D8)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.8. **EliminarConcomitancia** (H5)

a) Fórmulas: não há  
b) Formato:
```
#,##0
```

c) Regras de validação:
```VALUE_IN_LIST Sim,Não
```

d) Notas: não há  

### 2.9. **MarcosTemporais** (D6:D17)

a) Fórmulas:
```
=DPE+1
=DER
=DERReafirmada1
=DERReafirmada2
```

b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.10. **RotuloDERReafirmada1** (F11)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.11. **RotuloDERReafirmada2** (F12)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.12. **VigenciaPontos** (D9)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

## 3. Página "TCDiscriminado"

### 3.1. **ClassificacaoTCInformado1** (F:F)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_RANGE TabelaConversao!A:A
```

d) Notas: não há  

### 3.2. **DataFinalTCDiscriminado** (D:D)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.3. **DataInicialTCDiscriminado** (C:C)

a) Fórmulas: não há  
b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.4. **DescricaoTCDiscriminado** (A:A)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.5. **ErrosTCDiscriminado** (E:E)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(ErrosTCDiscriminado)=1;"Erros";IF(DataInicialTCDiscriminado*DataFinalTCDiscriminado;IF(MMULT((DataInicialTCDiscriminado<=TRANSPOSE(DataFinalTCDiscriminado))*(DataFinalTCDiscriminado>=TRANSPOSE(DataInicialTCDiscriminado));SIGN(ROW(DataInicialTCDiscriminado)))>1;"Concomitância";IF(DataFinalTCDiscriminado<DataInicialTCDiscriminado;"Final < Inicial";""));" ")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.6. **FatorConversaoTCDiscriminado** (H:H)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(FatorConversaoTCDiscriminado)=1;"Fator Conv.";IF(DataInicialTCDiscriminado*DataFinalTCDiscriminado;IF(FatorConversaoTCDiscriminadoModificado;FatorConversaoTCDiscriminadoModificado;IF(ReferenciaFatorTCDiscriminado="N";0;TCAposentadoriaIntegral/(IF(ReferenciaFatorTCDiscriminado="V";{" ";ReferenciaFatorTCDiscriminado};ReferenciaFatorTCDiscriminado))));"")))
```

b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.7. **FatorConversaoTCDiscriminadoModificado** (I:I)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.8. **MotivosTCDiscriminado** (J:J)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_RANGE ListaMotivos!A:A
```

d) Notas: não há  

### 3.9. **NaturezaTCDiscriminado** (B:B)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.10. **ObservacoesTCDiscriminado** (K:K)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.11. **ReferenciaFatorTCDiscriminado** (G:G)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(ReferenciaFatorTCDiscriminado)=1;"Referência";IF(DataInicialTCDiscriminado*DataFinalTCDiscriminado;IF(ClassificacaoTCInformado1<>"";VLOOKUP(ClassificacaoTCInformado1;TabelaConversao!A:C;IF(Sexo="Homem";2;3);FALSE);VLOOKUP("1 - Comum";TabelaConversao!A:C;IF(Sexo="Homem";2;3);FALSE));"")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.12. **TCInformado** (A:A)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

## 4. Página "TCAdicionado"

### 4.1. **AnosAdicionados** (B:B)

a) Fórmulas: não há  
b) Formato:
```
0.###############
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.2. **AnosConvertidosTCAdicionado** (P:P)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(AnosConvertidosTCAdicionado)=1;"Anos conv.";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;ROUNDDOWN(TotalDiasConvertidosTCAdicionado/360);"")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 4.3. **AnosTCAdicionado** (B:B)

a) Fórmulas: não há  
b) Formato:
```
0.###############
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.4. **AnosTCAdicionadoDemonstrativo** (E:E)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(AnosTCAdicionadoDemonstrativo)=1;"Anos";IF(AnosAdicionados+MesesAdicionados+DiasAdicionados;IF(AnosAdicionados="";0;AnosAdicionados);"")))
```

b) Formato:
```
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.5. **CarenciaTCAdicionado** (T:T)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(TotalDiasConvertidosTCAdicionado)=1;"Carência";IF(ISNUMBER(CarenciaTCAdicionadoModificada);CarenciaTCAdicionadoModificada; IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;IF(ContarCarenciaTCAdicionado="Não";0;ROUNDUP(TotalDiasTCAdicionado/30));""))))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 4.6. **CarenciaTCAdicionadoModificada** (U:U)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.7. **ClassificacaoTCAdicionado** (K:K)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_RANGE TabelaConversao!A:A
```

d) Notas: não há  

### 4.8. **ContarCarenciaTCAdicionado** (S:S)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_LIST Sim,Não
```

d) Notas: não há  

### 4.9. **DiasAdicionados** (D:D)

a) Fórmulas: não há  
b) Formato:
```
0.###############
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.10. **DiasConvertidosTCAdicionado** (R:R)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DiasConvertidosTCAdicionado)=1;"Dias conv.";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;TotalDiasConvertidosTCAdicionado-(AnosConvertidosTCAdicionado*360)-(MesesConvertidosTCAdicionado*30);"")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 4.11. **DiasTCAdicionado** (D:D)

a) Fórmulas: não há  
b) Formato:
```
0.###############
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.12. **DiasTCAdicionadoDemonstrativo** (G:G)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DiasTCAdicionadoDemonstrativo)=1;"Dias";IF(AnosAdicionados+MesesAdicionados+DiasAdicionados;IF(DiasAdicionados="";0;DiasAdicionados);"")))
```

b) Formato:
```
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.13. **FatorConversaoTCAdicionado** (M:M)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(FatorConversaoTCAdicionado)=1;"Fator";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;IF(FatorConversaoTCAdicionadoModificado;FatorConversaoTCAdicionadoModificado;IF(ReferenciaFatorTCAdicionado="N";0;TCAposentadoriaIntegral/(IF(ReferenciaFatorTCAdicionado="V";{" ";ReferenciaFatorTCAdicionado};ReferenciaFatorTCAdicionado))));"")))
```

b) Formato:
```
#,##0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.14. **FatorConversaoTCAdicionadoModificado** (N:N)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.15. **LimitesTCAdicionado** (H:H)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(LimitesTCAdicionado)=1;"Até...";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;IF(LimitesTCAdicionadoModificado;LimitesTCAdicionadoModificado;DER-1);"")))
```

b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.16. **LimitesTCAdicionadoModificado** (I:I)

a) Fórmulas: não há  
b) Formato:
```
0.###############
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.17. **MesesAdicionados** (C:C)

a) Fórmulas: não há  
b) Formato:
```
0.###############
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.18. **MesesConvertidosTCAdicionado** (Q:Q)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(MesesConvertidosTCAdicionado)=1;"Meses conv.";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;ROUNDDOWN((TotalDiasConvertidosTCAdicionado-(AnosConvertidosTCAdicionado*360))/30);"")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 4.19. **MesesTCAdicionado** (C:C)

a) Fórmulas: não há  
b) Formato:
```
0.###############
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.20. **MesesTCAdicionadoDemonstrativo** (F:F)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(MesesTCAdicionadoDemonstrativo)=1;"Meses";IF(AnosAdicionados+MesesAdicionados+DiasAdicionados;IF(MesesAdicionados="";0;MesesAdicionados);"")))
```

b) Formato:
```
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.21. **MotivosTCAdicionado** (V:V)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_RANGE ListaMotivos!A:A
```

d) Notas: não há  

### 4.22. **MotivosTCAdicionadoDemonstrativo** (X:X)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(MotivosTCAdicionadoDemonstrativo)=1;"Motivos Demonstrativo";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;IF(MotivosTCAdicionado="";" ";MID(MotivosTCAdicionado;5;100));"")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 4.23. **ObservacoesTCAdicionado** (W:W)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.24. **ObservacoesTCAdicionadoDemonstrativo** (Y:Y)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(ObservacoesTCAdicionadoDemonstrativo)=1;"Observacoes Demonstrativo";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;IF(ObservacoesTCAdicionado="";"";"Seq. "&ROW(ObservacoesTCAdicionado)&". "&ObservacoesTCAdicionado);"")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 4.25. **ReferenciaFatorTCAdicionado** (L:L)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(ReferenciaFatorTCAdicionado)=1;"Referência";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;IF(ClassificacaoTCAdicionado<>"";VLOOKUP(ClassificacaoTCAdicionado;TabelaConversao!A:B;IF(Sexo="Homem";2;3);FALSE);VLOOKUP("1 - Comum";TabelaConversao!A:B;IF(Sexo="Homem";2;3);FALSE));"")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 4.26. **SequenciaTCAdicionado** (A:A)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(SequenciaTCAdicionado)=1;"Seq";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;ROW(SequenciaTCAdicionado)-1;"")))
```

b) Formato:
```
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.27. **TotalDiasConvertidosTCAdicionado** (O:O)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(TotalDiasConvertidosTCAdicionado)=1;"Total conv.";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;TotalDiasTCAdicionado*FatorConversaoTCAdicionado;"")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 4.28. **TotalDiasTCAdicionado** (J:J)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(TotalDiasTCAdicionado)=1;"Total (dias)";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;(AnosTCAdicionadoDemonstrativo*360)+(MesesTCAdicionadoDemonstrativo*30)+DiasTCAdicionadoDemonstrativo;"")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

## 5. Página "Modificadores"

### 5.1. **AcrescimoModificado** (X4:X63)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 5.2. **Acrescimos** (W4:W63)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ISNUMBER(AcrescimoModificado);AcrescimoModificado;IF(ROW(Acrescimos)=4;"Acréscimos Lei 11.718/2008";IF(D4:D*E4:E;IF(MID(AplicarLei11718;1;1)="1";0;IF(AND(Especie=41;BeneficioRural="Sim");{" ";jef_CALCULAR_ACRESCIMOS_LEI_11718(D5:E;MID(AplicarLei11718;1;1)="3")};0));""))))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 5.3. **CarenciaTCDiscriminado** (U4:U62)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ISNUMBER(CarenciaTCDiscriminadoModificada);CarenciaTCDiscriminadoModificada;IF(ROW(CarenciaTCDiscriminado)=4;"Carência";IF(ROW(CarenciaTCDiscriminado)>COUNTA(DataInicialTCDiscriminadoProcessado)+3;"";IF(ContarCarenciaTCDiscriminado<>"Não";IF(MesmoMes;1;IF(MesmoAno;MONTH(DataFinalTCDiscriminadoProcessado)-MONTH(DataInicialTCDiscriminadoProcessado)+1;(12-MONTH(DataInicialTCDiscriminadoProcessado)+1+MONTH(DataFinalTCDiscriminadoProcessado)+((YEAR(DataFinalTCDiscriminadoProcessado)-YEAR(DataInicialTCDiscriminadoProcessado)-1)*12))))-IF(ContinuaAnterior*{TRUE;ContarCarenciaTCDiscriminado<>"Não"};1;0);0)))))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 5.4. **CarenciaTCDiscriminadoModificada** (V4:V62)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 5.5. **ContarCarenciaTCDiscriminado** (T4:T63)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação:
```VALUE_IN_LIST Sim,Não
```

d) Notas: não há  

### 5.6. **MotivosTCDiscriminadoDemonstrativo** (R4:R63)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(MotivosTCDiscriminadoDemonstrativo)=4;"Motivos Demonstrativo";IF(DataInicialTCDiscriminadoProcessado*DataFinalTCDiscriminadoProcessado;IF(MotivosTCDiscriminadoProcessado="";" ";" ("&MID(MotivosTCDiscriminadoProcessado;1;1)&")");"")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 5.7. **ObservacoesTCDiscriminadoDemonstrativo** (S4:S63)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(ObservacoesTCDiscriminadoDemonstrativo)=4;"Observacoes Demonstrativo";IF(DataInicialTCDiscriminadoProcessado*DataFinalTCDiscriminadoProcessado;IF(ObservacoesTCDiscriminadoProcessado="";"";"Seq. "&ROW(ObservacoesTCDiscriminadoProcessado)-1&". "&ObservacoesTCDiscriminadoProcessado);"")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 5.8. **SequenciaTCDiscriminado** (C4:C63)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(SequenciaTCDiscriminado)=4;"Seq";IF(DataInicialTCDiscriminadoProcessado;ROW(SequenciaTCDiscriminado)-4;"")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  
