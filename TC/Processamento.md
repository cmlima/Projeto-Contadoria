# III. Processamento

## 1. Página "Processamento"

### 1.1. **AnosConvertidosTCDiscriminadoProcessado** (AG:AG)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(AnosConvertidosTCDiscriminadoProcessado)=1;"Anos conv.";IF(ROW(AnosConvertidosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN(TotalDiasConvertidosTCDiscriminadoProcessado/360))))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 1.2. **AnosTCDiscriminadoProcessado** (AC:AC)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(AnosTCDiscriminadoProcessado)=1;"Anos";IF(ROW(AnosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN(TotalDiasTCDiscriminadoProcessado/360))))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 1.3. **ClassificacaoTCDiscriminado** (Z:Z)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.4. **ContinuaAnterior** (AL:AL)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(ContinuaAnterior)=1;"Continua ant.";IF(ROW(ContinuaAnterior)>COUNTA(DataInicialTCDiscriminadoProcessado);"";IF(ROW(ContinuaAnterior)=2;FALSE;EOMONTH({"";DataFinalTCDiscriminadoProcessado};0)=EOMONTH(DataInicialTCDiscriminadoProcessado;0)))))
```

b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.5. **DataFinalTCDiscriminadoProcessado** (U:U)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.6. **DataInicialTCDiscriminadoProcessado** (T:T)

a) Fórmulas:
```
={"Data inicial"\"Data final"\"Descrição"\"Natureza"\"Motivos"\"Observações"\"Classificação"\"Fator";
IF(AjustarMarcosTemporais="Sim";jef_ESTABELECER_MARCOS_TEMPORAIS(K2:R;MarcosTemporais);K2:R)}
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.7. **DescricaoTCDiscriminadoProcessado** (V:V)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.8. **DiasConvertidosTCDiscriminadoProcessado** (AI:AI)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DiasConvertidosTCDiscriminadoProcessado)=1;"Dias conv.";IF(ROW(DiasConvertidosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";TotalDiasConvertidosTCDiscriminadoProcessado-(AnosConvertidosTCDiscriminadoProcessado*360)-(MesesConvertidosTCDiscriminadoProcessado*30))))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 1.9. **DiasTCDiscriminadoProcessado** (AE:AE)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(DiasTCDiscriminadoProcessado)=1;"Dias";IF(ROW(DiasTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";TotalDiasTCDiscriminadoProcessado-(AnosTCDiscriminadoProcessado*360)-(MesesTCDiscriminadoProcessado*30))))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 1.10. **FatorConversaoTCDiscriminadoProcessado** (AA:AA)

a) Fórmulas: não há  
b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.11. **MesesConvertidosTCDiscriminadoProcessado** (AH:AH)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(MesesConvertidosTCDiscriminadoProcessado)=1;"Meses conv.";IF(ROW(MesesConvertidosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN((TotalDiasConvertidosTCDiscriminadoProcessado-(AnosConvertidosTCDiscriminadoProcessado*360))/30))))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 1.12. **MesesTCDiscriminadoProcessado** (AD:AD)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(MesesTCDiscriminadoProcessado)=1;"Meses";IF(ROW(MesesTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN((TotalDiasTCDiscriminadoProcessado-(AnosTCDiscriminadoProcessado*360))/30))))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 1.13. **MesmoAno** (AJ:AJ)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(MesmoAno)=1;"Mesmo Ano";IF(ROW(MesmoAno)>COUNTA(DataInicialTCDiscriminadoProcessado);"";YEAR(DataInicialTCDiscriminadoProcessado)=YEAR(DataFinalTCDiscriminadoProcessado))))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 1.14. **MesmoMes** (AK:AK)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(MesmoMes)=1;"Mesmo Mês";IF(ROW(MesmoMes)>COUNTA(DataInicialTCDiscriminadoProcessado);"";EOMONTH(DataInicialTCDiscriminadoProcessado;0)=EOMONTH(DataFinalTCDiscriminadoProcessado;0))))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 1.15. **MotivosTCDiscriminadoProcessado** (X:X)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.16. **NaturezaTCDiscriminadoProcessado** (W:W)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.17. **ObservacoesTCDiscriminadoProcessado** (Y:Y)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.18. **TCProcessado** (A:A)

a) Fórmulas:
```
={DataInicialTCDiscriminado\DataFinalTCDiscriminado\DescricaoTCDiscriminado\NaturezaTCDiscriminado\MotivosTCDiscriminado\ObservacoesTCDiscriminado\ARRAYFORMULA(IF(ROW(ClassificacaoTCInformado1)>COUNTA(DataInicialTCDiscriminado);"";IF(ClassificacaoTCInformado1="";"1 - Comum";ClassificacaoTCInformado1)))\FatorConversaoTCDiscriminado}
```

b) Formato:
```
dd/MM/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.19. **TotalDiasConvertidosTCDiscriminadoProcessado** (AF:AF)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(TotalDiasConvertidosTCDiscriminadoProcessado)=1;"Total conv.";IF(ROW(TotalDiasConvertidosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN(DAYS360(DataInicialTCDiscriminadoProcessado;DataFinalTCDiscriminadoProcessado)*FatorConversaoTCDiscriminadoProcessado))))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 1.20. **TotalDiasTCDiscriminadoProcessado** (AB:AB)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(TotalDiasTCDiscriminadoProcessado)=1;"Total (dias)";IF(ROW(TotalDiasTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";DAYS360(DataInicialTCDiscriminadoProcessado;DataFinalTCDiscriminadoProcessado+1))))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

## 2. Página "Parametros"

### 2.1. **CarenciaMinimaDER** (B8)

a) Fórmulas:
```
=IFERROR(IF(MIN(DataInicialTCDiscriminadoProcessado)>=DLB;180;INDEX(TabelaCarencia!A:B;MATCH(YEAR(DER-1);TabelaCarencia!A:A;1);2));180)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.2. **CarenciaMinimaDERReafirmada1** (B9)

a) Fórmulas:
```
=IFERROR(IF(MIN(DataInicialTCDiscriminadoProcessado)>=DLB;180;INDEX(TabelaCarencia!A:B;MATCH(YEAR(DERReafirmada1-1);TabelaCarencia!A:A;1);2));180)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.3. **CarenciaMinimaDERReafirmada2** (B10)

a) Fórmulas:
```
=IFERROR(IF(MIN(DataInicialTCDiscriminadoProcessado)>=DLB;180;INDEX(TabelaCarencia!A:B;MATCH(YEAR(DERReafirmada2-1);TabelaCarencia!A:A;1);2));180)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.4. **CarenciaMinimaDPE** (B6)

a) Fórmulas:
```
=IFERROR(IF(MIN(DataInicialTCDiscriminadoProcessado)>=DLB;180;INDEX(TabelaCarencia!A:B;MATCH(YEAR(DPE);TabelaCarencia!A:A;1);2));180)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.5. **CarenciaMinimaDPL** (B7)

a) Fórmulas:
```
=IFERROR(IF(MIN(DataInicialTCDiscriminadoProcessado)>=DLB;180;INDEX(TabelaCarencia!A:B;MATCH(YEAR(DPL-1);TabelaCarencia!A:A;1);2));180)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.6. **CarenciaMinimaIdade** (B5)

a) Fórmulas:
```
=IFERROR(IF(MIN(DataInicialTCDiscriminadoProcessado)>=DLB;180;INDEX(TabelaCarencia!A:B;MATCH(YEAR(DataNascimento)+IdadeMinima;TabelaCarencia!A:A;1);2));180)
```

b) Formato:
```
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.7. **ComputarPedagio** (B3)

a) Fórmulas:
```
=AND(Especie=42;TotalDiasDPE>0;TotalDiasFaltantesComPedagio>0;TotalDiasFaltantesComPedagio+TotalDiasDPE<(IF(Sexo="Mulher";30;35)*360))
```

b) Formato:
```
mm"/"yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.8. **DireitoAdquiridoDPE** (B12)

a) Fórmulas:
```
=AND(TotalCarenciaDPE>=CarenciaDPE;TotalDiasDPE>=TotalDiasTCMinimoDPE)
```

b) Formato:
```
mm"/"yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.9. **IdadeMinima** (B4)

a) Fórmulas:
```
=IF(Especie=41;IF(BeneficioRural="Sim";IF(Sexo="Homem";60;55);IF(Sexo="Homem";65;60));IF(ComputarPedagio;IF(Sexo="Mulher";48;53);0))
```

b) Formato:
```
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.10. **PontuacaoMinimaDER** (B14)

a) Fórmulas:
```
=IF(AND(Especie=42;DER>=VigenciaPontos);INDEX(TabelaPontuacao!A:C;MATCH(DER-1;TabelaPontuacao!A:A;1);IF(Sexo="Homem";2;3));"não se aplica")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.11. **PontuacaoMinimaDERReafirmada1** (B15)

a) Fórmulas:
```
=IF(AND(Especie=42;DERReafirmada1>=VigenciaPontos);INDEX(TabelaPontuacao!A:C;MATCH(DERReafirmada1-1;TabelaPontuacao!A:A;1);IF(Sexo="Homem";2;3));"não se aplica")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.12. **PontuacaoMinimaDERReafirmada2** (B16)

a) Fórmulas:
```
=IF(AND(Especie=42;DERReafirmada2>=VigenciaPontos);INDEX(TabelaPontuacao!A:C;MATCH(DERReafirmada2-1;TabelaPontuacao!A:A;1);IF(Sexo="Homem";2;3));"não se aplica")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.13. **TotalDiasTCMinimo** (B13)

a) Fórmulas:
```
=IF(Especie=42;IF(ComputarPedagio;MIN(TotalDiasDPE+TotalDiasFaltantesComPedagio;IF(Sexo="Homem";35*360;30*360));IF(DireitoAdquiridoDPE;IF(Sexo="Homem";30*360;25*360);TCAposentadoriaIntegral*360));TCAposentadoriaIntegral*360)
```

b) Formato:
```
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.14. **TotalDiasTCMinimoDPE** (B11)

a) Fórmulas:
```
=IF(Especie=42;IF(Sexo="Homem";30*360;25*360);0)
```

b) Formato:
```
0
```

c) Regras de validação: não há  
d) Notas: não há  

## 3. Página "Resultado"

### 3.1. **AnosDER** (F10)

a) Fórmulas:
```
=ROUNDDOWN(E10/360)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.2. **AnosDERReafirmada1** (F11)

a) Fórmulas:
```
=IF(ISNUMBER(E11);ROUNDDOWN(E11/360);"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.3. **AnosDERReafirmada2** (F12)

a) Fórmulas:
```
=IF(ISNUMBER(E12);ROUNDDOWN(E12/360);"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.4. **AnosDPE** (F5)

a) Fórmulas:
```
=ROUNDDOWN(E5/360)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.5. **AnosDPL** (F9)

a) Fórmulas:
```
=ROUNDDOWN(E9/360)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.6. **AnosFaltantesComPedagio** (F7)

a) Fórmulas:
```
=ROUNDDOWN(E7/360)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.7. **AnosPedagio** (F6)

a) Fórmulas:
```
=ROUNDDOWN(E6/360)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.8. **AnosTCMinimo** (F8)

a) Fórmulas:
```
=ROUNDDOWN(E8/360)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.9. **BeneficioIntegralDER** (M10)

a) Fórmulas:
```
=TotalDiasDER>=TCAposentadoriaIntegral*360
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.10. **BeneficioIntegralDERReafirmada1** (M11)

a) Fórmulas:
```
=TotalDiasDERReafirmada1>=TCAposentadoriaIntegral*360
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.11. **BeneficioIntegralDERReafirmada2** (M12)

a) Fórmulas:
```
=TotalDiasDERReafirmada2>=TCAposentadoriaIntegral*360
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.12. **BeneficioIntegralDPE** (M5)

a) Fórmulas:
```
=TotalDiasDPE>=TCAposentadoriaIntegral*360
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.13. **BeneficioIntegralDPL** (M9)

a) Fórmulas:
```
=TotalDiasDPL>=TCAposentadoriaIntegral*360
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.14. **CarenciaDER** (I10)

a) Fórmulas:
```
=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DER;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<"&DER;CarenciaTCAdicionado)
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.15. **CarenciaDERReafirmada1** (I11)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada1);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada1;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<"&DERReafirmada1;CarenciaTCAdicionado);"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.16. **CarenciaDERReafirmada2** (I12)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);SUMIF(DataFinalTCDiscriminadoProcessado;"<="&DERReafirmada2;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<="&DERReafirmada2;CarenciaTCAdicionado);"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.17. **CarenciaDPE** (I5)

a) Fórmulas:
```
=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPEMaisUm;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<"&DPEMaisUm;CarenciaTCAdicionado)
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.18. **CarenciaDPL** (I9)

a) Fórmulas:
```
=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPL;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<"&DPL;CarenciaTCAdicionado)
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.19. **CoeficienteDER** (N10)

a) Fórmulas:
```
=IF(DireitoAoBeneficioDER;IF(BeneficioIntegralDER;1;MIN(((ROUNDDOWN(TotalDiasDER/360)-ROUNDDOWN(TotalDiasTCMinimo/360))*0,05)+0,7;1));"")
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.20. **CoeficienteDERReafirmada1** (N11)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada1);IF(BeneficioIntegralDERReafirmada1;1;IF(DireitoAoBeneficioDERReafirmada1;MIN((ROUNDDOWN((TotalDiasDERReafirmada1-TotalDiasTCMinimo)/360)*0,05)+0,7;1);""));"")
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.21. **CoeficienteDERReafirmada2** (N12)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);IF(BeneficioIntegralDERReafirmada2;1;IF(DireitoAoBeneficioDERReafirmada2;MIN((ROUNDDOWN((TotalDiasDERReafirmada2-TotalDiasTCMinimo)/360)*0,05)+0,7;1);""));"")
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.22. **CoeficienteDPE** (N5)

a) Fórmulas:
```
=IF(DireitoAoBeneficioDPE;IF(BeneficioIntegralDPE;1;MIN((ROUNDDOWN((TotalDiasDPE-TotalDiasTCMinimoDPE)/360)*0,06)+0,7;1));"")
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.23. **CoeficienteDPL** (N9)

a) Fórmulas:
```
=IF(DireitoAoBeneficioDPL;IF(BeneficioIntegralDPL;1;MIN(((ROUNDDOWN(TotalDiasDPL/360)-ROUNDDOWN(TotalDiasTCMinimo/360))*0,05)+0,7;1));"")
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.24. **DPE** (B5)

a) Fórmulas: não há  
b) Formato:
```
d/m/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.25. **DiasDER** (H10)

a) Fórmulas:
```
=E10-(F10*360)-(G10*30)
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.26. **DiasDERReafirmada1** (H11)

a) Fórmulas:
```
=IF(ISNUMBER(E11);E11-(F11*360)-(G11*30);"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.27. **DiasDERReafirmada2** (H12)

a) Fórmulas:
```
=IF(ISNUMBER(E12);E12-(F12*360)-(G12*30);"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.28. **DiasDPE** (H5)

a) Fórmulas:
```
=E5-(F5*360)-(G5*30)
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.29. **DiasDPL** (H9)

a) Fórmulas:
```
=E9-(F9*360)-(G9*30)
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.30. **DiasFaltantesPedagio** (H7)

a) Fórmulas:
```
=ROUNDDOWN(E7-(F7*360)-(G7*30))
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.31. **DiasPedagio** (H6)

a) Fórmulas:
```
=ROUNDDOWN(E6-(F6*360)-(G6*30))
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.32. **DiasTCMinimo** (H8)

a) Fórmulas:
```
=ROUNDDOWN(E8-(F8*360)-(G8*30))
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.33. **DireitoAoBeneficioDER** (L10)

a) Fórmulas:
```
=AND(IdadeDER>=IdadeMinima;TotalCarenciaDER>=CarenciaDER;TotalDiasDER>=TotalDiasTCMinimo)
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.34. **DireitoAoBeneficioDERReafirmada1** (L11)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada1);AND(IdadeDERReafirmada1>=IdadeMinima;TotalCarenciaDERReafirmada1>=CarenciaDERReafirmada1;TotalDiasDERReafirmada1>=TotalDiasTCMinimo);"")
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.35. **DireitoAoBeneficioDERReafirmada2** (L12)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);AND(IdadeDERReafirmada2>=IdadeMinima;TotalCarenciaDERReafirmada2>=CarenciaDERReafirmada2;TotalDiasDERReafirmada2>=TotalDiasTCMinimo);"")
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.36. **DireitoAoBeneficioDPE** (L5)

a) Fórmulas:
```
=AND(TotalCarenciaDPE>=CarenciaDPE;TotalDiasDPE>=TotalDiasTCMinimoDPE)
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.37. **DireitoAoBeneficioDPL** (L9)

a) Fórmulas:
```
=AND(IdadeDPL>=IdadeMinima;TotalCarenciaDPL>=CarenciaDPL;TotalDiasDPL>=TotalDiasTCMinimo)
```

b) Formato:
```
0%
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.38. **IdadeDER** (C10)

a) Fórmulas:
```
=DAYS360(DataNascimento;DER-1)/360
```

b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.39. **IdadeDERReafirmada1** (C11)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada1);DAYS360(DataNascimento;DERReafirmada1-1)/360;"")
```

b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.40. **IdadeDERReafirmada2** (C12)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);DAYS360(DataNascimento;DERReafirmada2-1)/360;"")
```

b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.41. **IdadeDPE** (C5)

a) Fórmulas:
```
=DAYS360(DataNascimento;DPE)/360
```

b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.42. **IdadeDPL** (C9)

a) Fórmulas:
```
=DAYS360(DataNascimento;DPL-1)/360
```

b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.43. **MesesDER** (G10)

a) Fórmulas:
```
=ROUNDDOWN((E10-(F10*360))/30)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.44. **MesesDERReafirmada1** (G11)

a) Fórmulas:
```
=IF(ISNUMBER(E11);ROUNDDOWN((E11-(F11*360))/30);"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.45. **MesesDERReafirmada2** (G12)

a) Fórmulas:
```
=IF(ISNUMBER(E12);ROUNDDOWN((E12-(F12*360))/30);"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.46. **MesesDPE** (G5)

a) Fórmulas:
```
=ROUNDDOWN((E5-(F5*360))/30)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.47. **MesesDPL** (G9)

a) Fórmulas:
```
=ROUNDDOWN((E9-(F9*360))/30)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.48. **MesesFaltantesComPedagio** (G7)

a) Fórmulas:
```
=ROUNDDOWN((E7-(F7*360))/30)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.49. **MesesPedagio** (G6)

a) Fórmulas:
```
=ROUNDDOWN((E6-(F6*360))/30)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.50. **MesesTCMinimo** (G8)

a) Fórmulas:
```
=ROUNDDOWN((E8-(F8*360))/30)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.51. **PontosDER** (D10)

a) Fórmulas:
```
=IF(AND(Especie=42;DER>=VigenciaPontos);(TotalDiasDER/360)+IdadeDER;"")
```

b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.52. **PontosDERReafirmada1** (D11)

a) Fórmulas:
```
=IF(AND(Especie=42;DERReafirmada1>=VigenciaPontos);(TotalDiasDER/360)+IdadeDERReafirmada1;"")
```

b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.53. **PontosDERReafirmada2** (D12)

a) Fórmulas:
```
=IF(AND(Especie=42;DERReafirmada2>=VigenciaPontos);(TotalDiasDER/360)+IdadeDERReafirmada2;"")
```

b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.54. **TotalAcrescimosDER** (J10)

a) Fórmulas:
```
=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DER;Acrescimos)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.55. **TotalAcrescimosDERReafirmada1** (J11)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada1);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada1;Acrescimos);"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.56. **TotalAcrescimosDERReafirmada2** (J12)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada2;Acrescimos);"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.57. **TotalAcrescimosDPE** (J5)

a) Fórmulas:
```
=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPEMaisUm;Acrescimos)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.58. **TotalAcrescimosDPL** (J9)

a) Fórmulas:
```
=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPL;Acrescimos)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.59. **TotalCarenciaDER** (K10)

a) Fórmulas:
```
=CarenciaDER+TotalAcrescimosDER
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.60. **TotalCarenciaDERReafirmada1** (K11)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);CarenciaDERReafirmada1+TotalAcrescimosDERReafirmada1;"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.61. **TotalCarenciaDERReafirmada2** (K12)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);CarenciaDERReafirmada2+TotalAcrescimosDERReafirmada2;"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.62. **TotalCarenciaDPE** (K5)

a) Fórmulas:
```
=CarenciaDPE+TotalAcrescimosDPE
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.63. **TotalCarenciaDPL** (K9)

a) Fórmulas:
```
=CarenciaDPL+TotalAcrescimosDPL
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.64. **TotalDiasDER** (E10)

a) Fórmulas:
```
=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DER;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DER;TotalDiasConvertidosTCAdicionado)


```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.65. **TotalDiasDERReafirmada1** (E11)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada1);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada1;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DERReafirmada1;TotalDiasConvertidosTCAdicionado);"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.66. **TotalDiasDERReafirmada2** (E12)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada2;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DERReafirmada2;TotalDiasConvertidosTCAdicionado);"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.67. **TotalDiasDPE** (E5)

a) Fórmulas:
```
=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPEMaisUm;TotalDiasTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DPEMaisUm;TotalDiasTCAdicionado)
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.68. **TotalDiasDPL** (E9)

a) Fórmulas:
```
=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPL;TotalDiasTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DPL;TotalDiasTCAdicionado)
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.69. **TotalDiasFaltantesComPedagio** (E7)

a) Fórmulas:
```
=((IF(Sexo="Mulher";25;30)*360)+TotalDiasPedagio)-TotalDiasDPE
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.70. **TotalDiasPedagio** (E6)

a) Fórmulas:
```
=((IF(Sexo="Mulher";25;30)*360)-TotalDiasDPE)*0,4
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

## 4. Página "ParametrosDemonstrativos"

### 4.1. **DadosObrigatoriosFaltantes** (B28)

a) Fórmulas:
```
=IF(LEN(Sexo)>0;"";"Sexo#")& IF(ISNUMBER(DataNascimento);"";"Nascimento#")&IF(ISNUMBER(Especie);"";"Espécie#")&IF(ISNUMBER(DER);"";"DER#")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.2. **ObservacoesPeriodosAdicionados** (B23)

a) Fórmulas:
```
=JOIN(CHAR(10);FILTER(OFFSET(ObservacoesTCAdicionadoDemonstrativo;1;0);OFFSET(ObservacoesTCAdicionadoDemonstrativo;1;0)<>""))
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.3. **ObservacoesPeriodosDiscriminados** (B20)

a) Fórmulas:
```
=JOIN(CHAR(10);FILTER(OFFSET(ObservacoesTCDiscriminadoDemonstrativo;1;0);OFFSET(ObservacoesTCDiscriminadoDemonstrativo;1;0)<>""))
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.4. **TemPeriodosAdicionados** (D23)

a) Fórmulas:
```
=NOT(NOT(SUM(ARRAYFORMULA(ISNUMBER(AnosTCAdicionadoDemonstrativo)*ISNUMBER(MesesTCAdicionadoDemonstrativo)*ISNUMBER(COUNTA(DiasTCAdicionadoDemonstrativo))))))
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.5. **TextoAnosDER** (L5)

a) Fórmulas:
```
=TEXT(AnosDER;"0")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.6. **TextoAnosDERReafirmada1** (N5)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada1);TEXT(AnosDERReafirmada1;"0");"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.7. **TextoAnosDERReafirmada2** (P5)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);TEXT(AnosDERReafirmada2;"0");"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.8. **TextoAnosDPE** (B5)

a) Fórmulas:
```
=TEXT(AnosDPE;"0")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.9. **TextoAnosDPL** (J5)

a) Fórmulas:
```
=TEXT(AnosDPL;"0")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.10. **TextoAnosFaltantesComPedagio** (F5)

a) Fórmulas:
```
=IF(ComputarPedagio;TEXT(AnosFaltantesComPedagio;"0");0)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.11. **TextoAnosPedagio** (D5)

a) Fórmulas:
```
=IF(ComputarPedagio;TEXT(AnosPedagio;"0");" ")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.12. **TextoAnosTCMinimo** (H5)

a) Fórmulas:
```
=IF(ComputarPedagio;TEXT(AnosTCMinimo;"0");0)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.13. **TextoCarenciaDER** (L11)

a) Fórmulas:
```
=TEXT(CarenciaDER;"0")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.14. **TextoCarenciaDERReafirmada1** (N11)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada1);TEXT(CarenciaDERReafirmada1;"0");"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.15. **TextoCarenciaDERReafirmada2** (P11)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);TEXT(CarenciaDERReafirmada2;"0");"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.16. **TextoCarenciaDPE** (B11)

a) Fórmulas:
```
=TEXT(CarenciaDPE;"0")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.17. **TextoCarenciaDPL** (J11)

a) Fórmulas:
```
=TEXT(CarenciaDPL;"0")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.18. **TextoCarenciaPedagio** (D11)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.19. **TextoCarenciaTCMinimo** (H11)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.20. **TextoCarenciaTempoFaltante** (F11)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.21. **TextoCoeficienteDER** (L13)

a) Fórmulas:
```
=TEXT(CoeficienteDER;"0%")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.22. **TextoCoeficienteDERReafirmada1** (N13)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada1);TEXT(CoeficienteDERReafirmada1;"0%");"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.23. **TextoCoeficienteDERReafirmada2** (P13)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);TEXT(CoeficienteDERReafirmada2;"0%");"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.24. **TextoCoeficienteDPE** (B13)

a) Fórmulas:
```
=IF(DireitoAoBeneficioDPE;TEXT(CoeficienteDPE;"0%");" ")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.25. **TextoCoeficienteDPL** (J13)

a) Fórmulas:
```
=IF(DireitoAoBeneficioDPL;TEXT(CoeficienteDPL;"0%");" ")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.26. **TextoCoeficientePedagio** (D13)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.27. **TextoCoeficienteTCMinimo** (H13)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.28. **TextoCoeficienteTempoFaltante** (F13)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.29. **TextoDER** (L3)

a) Fórmulas:
```
=CHAR(9)&TEXT(DER;"dd/mm/yyyy")&" (DER)"
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.30. **TextoDERReafirmada1** (N3)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada1);CHAR(9)&TEXT(DERReafirmada1;"dd/mm/yyyy")&" ("&RotuloDERReafirmada1&")";"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.31. **TextoDERReafirmada2** (P3)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);CHAR(9)&TEXT(DERReafirmada2;"dd/mm/yyyy")&" ("&RotuloDERReafirmada2&")";"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.32. **TextoDPE** (B3)

a) Fórmulas:
```
=CHAR(9)&TEXT(DPE;"dd/mm/yyyy")&" (DPE)"
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.33. **TextoDPL** (J3)

a) Fórmulas:
```
=CHAR(9)&TEXT(DPL;"dd/mm/yyyy")&" (DPL)"
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.34. **TextoDiasDER** (L9)

a) Fórmulas:
```
=TEXT(DiasDER;"0")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.35. **TextoDiasDERReafirmada1** (N9)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada1);TEXT(DiasDERReafirmada1;"0");"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.36. **TextoDiasDERReafirmada2** (P9)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);TEXT(DiasDERReafirmada2;"0");"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.37. **TextoDiasDPE** (B9)

a) Fórmulas:
```
=TEXT(DiasDPE;"0")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.38. **TextoDiasDPL** (J9)

a) Fórmulas:
```
=TEXT(DiasDPL;"0")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.39. **TextoDiasFaltantesComPedagio** (F9)

a) Fórmulas:
```
=IF(ComputarPedagio;TEXT(DiasFaltantesPedagio;"0");0)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.40. **TextoDiasPedagio** (D9)

a) Fórmulas:
```
=IF(ComputarPedagio;TEXT(DiasPedagio;"0");" ")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.41. **TextoDiasTCMinimo** (H9)

a) Fórmulas:
```
=IF(ComputarPedagio;TEXT(DiasTCMinimo;"0");0)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.42. **TextoIdadeDER** (L15)

a) Fórmulas:
```
=TEXT(IdadeDER;"0.00")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.43. **TextoIdadeDERReafirmada1** (N15)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada1);TEXT(IdadeDERReafirmada1;"0.00");"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.44. **TextoIdadeDERReafirmada2** (P15)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);TEXT(IdadeDERReafirmada2;"0.00");"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.45. **TextoIdadeDPE** (B15)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.46. **TextoIdadeDPL** (J15)

a) Fórmulas:
```
=TEXT(IdadeDPL;"0.00")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.47. **TextoIdadePedagio** (D15)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.48. **TextoIdadeTCMinimo** (H15)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.49. **TextoIdadeTempoFaltante** (F15)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.50. **TextoMesesDER** (L7)

a) Fórmulas:
```
=TEXT(MesesDER;"0")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.51. **TextoMesesDERReafirmada1** (N7)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada1);TEXT(MesesDERReafirmada1;"0");"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.52. **TextoMesesDERReafirmada2** (P7)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);TEXT(MesesDERReafirmada2;"0");"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.53. **TextoMesesDPE** (B7)

a) Fórmulas:
```
=TEXT(MesesDPE;"0")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.54. **TextoMesesDPL** (J7)

a) Fórmulas:
```
=TEXT(MesesDPL;"0")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.55. **TextoMesesFaltantesComPedagio** (F7)

a) Fórmulas:
```
=IF(ComputarPedagio;TEXT(MesesFaltantesComPedagio;"0");0)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.56. **TextoMesesPedagio** (D7)

a) Fórmulas:
```
=IF(ComputarPedagio;TEXT(MesesPedagio;"0");" ")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.57. **TextoMesesTCMinimo** (H7)

a) Fórmulas:
```
=IF(ComputarPedagio;TEXT(MesesTCMinimo;"0");0)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.58. **TextoObservacoes** (D20)

a) Fórmulas:
```
=IF(MostrarObservacoesAutomaticas="Sim";IFERROR("Observações períodos discriminados:"&CHAR(10)&CONCATENATE(ObservacoesPeriodosDiscriminados)&CHAR(10)&CHAR(10);"")&IFERROR("Observações períodos adicionados:"&CHAR(10)&CONCATENATE(ObservacoesPeriodosAdicionados)&CHAR(10)&CHAR(10);"");"")&IF(ISTEXT(ObservacoesFinais);"Observações finais:"&CHAR(10)&ObservacoesFinais;"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.59. **TextoPedagio** (D3)

a) Fórmulas:
```
=CHAR(9)&"Pedágio "&IF(ComputarPedagio;"("&TEXT(TotalDiasPedagio;"0.00")&" dias)";"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.60. **TextoPontosDER** (L17)

a) Fórmulas:
```
=IF(ISNUMBER(PontosDER);TEXT(PontosDER;"0.00");" ")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.61. **TextoPontosDERReafirmada1** (N17)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada1);IF(ISNUMBER(PontosDERReafirmada1);TEXT(PontosDERReafirmada1;"0.00");" ");"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.62. **TextoPontosDERReafirmada2** (P17)

a) Fórmulas:
```
=IF(ISNUMBER(DERReafirmada2);IF(ISNUMBER(PontosDERReafirmada2);TEXT(PontosDERReafirmada2;"0.00");" ");"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.63. **TextoPontosDPE** (B17)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.64. **TextoPontosDPL** (J17)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.65. **TextoPontosPedagio** (D17)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.66. **TextoPontosTCMinimo** (H17)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.67. **TextoPontosTempoFaltante** (F17)

a) Fórmulas:
```
=" "
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.68. **TextoTCMinimo** (H3)

a) Fórmulas:
```
=CHAR(9)&"Tempo mínimo "&IF(ComputarPedagio;"("&TEXT(TotalDiasTCMinimo;"0.00")&" dias)";"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.69. **TextoTempoFaltanteComPedagio** (F3)

a) Fórmulas:
```
=CHAR(9)&"Tempo faltante com pedágio "&IF(DireitoAdquiridoDPE;"";"("&TEXT(TotalDiasFaltantesComPedagio;"0.00")&" dias)")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  
