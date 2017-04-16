# III. Processamento

## 1. Página "CalculoSalarios"

### 1.1. **Concomitancia** (C:C)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(OFFSET(D1;0;0;COUNTA(Salarios!A6:A);1))=1;"Concomitância";MMULT(IF(ISNUMBER(OFFSET(Salarios!D6;0;0;COUNTA(Salarios!A6:A);COLUMNS(Salarios!6:6)-3));SIGN(OFFSET(Salarios!D6;0;0;COUNTA(Salarios!A6:A);COLUMNS(Salarios!6:6)-3));0);TRANSPOSE(SIGN(COLUMN(OFFSET(Salarios!D6;0;0;1;COLUMNS(Salarios!6:6)-3)))))>=2))
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 1.2. **ResultadoSalariosFornecidos** (B:B)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(OFFSET(D1;0;0;COUNTA(Salarios!A6:A);1))=1;"Soma";MMULT(IF(ISNUMBER(OFFSET(D1;0;0;COUNTA(Salarios!A6:A);COLUMNS(D1:1)));OFFSET(D1;0;0;COUNTA(Salarios!A6:A);COLUMNS(D1:1));0);TRANSPOSE(SIGN(COLUMN(OFFSET(D1;0;0;1;COLUMNS(D1:1))))))))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

## 2. Página "ParametrosRMI"

### 2.1. **AplicacaoProgressivaFatorPrevidenciario** (B18)

a) Fórmulas:
```
=IF(AND(DDA>=DATE(1999;11;29);DDA<=DATE(1999;11;30));1;MIN(DATEDIF(DATE(1999;12;1);DDA;"M")+1;60))
```

b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.2. **BaseIndiceTeto** (B29)

a) Fórmulas:
```
=IF(OR(MID(CriterioPC;1;1)="1";MID(CriterioPC;1;1)="2");IF(ApurarIndiceTetoComFatorPrevidenciario="SIM";SalarioBeneficio;MAX(SalarioBeneficio;MediaSemFatorPrevidenciario));SalarioBeneficio)
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.3. **CompetenciaFinal** (B4)

a) Fórmulas:
```
=EOMONTH(DDA;-2)+1
```

b) Formato:
```
mm"/"yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.4. **CompetenciaInicial** (B3)

a) Fórmulas:
```
=IF(OR(MID(CriterioPC;1;1)="4";MID(CriterioPC;1;1)="5");EDATE(DDA;-48);IF(MID(CriterioPC;1;1)="3";EDATE(DDA;-48);DATE(1994;7;1)))
```

b) Formato:
```
mm"/"yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.5. **DivisorConsiderado** (B14)

a) Fórmulas:
```
=MAX(PCConsiderado;DivisorMinimo)
```

b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.6. **DivisorMinimo** (B10)

a) Fórmulas:
```
=IF(MID(CriterioPC;1;1)="2";ROUNDDOWN(TotalCompetencias*0,6);IF(MID(CriterioPC;1;1)="3";12;IF(MID(CriterioPC;1;1)="5";24;TotalSalariosDDA)))
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.7. **FatorPrevidenciario** (B17)

a) Fórmulas:
```
=(TCTotalDias/360)*0,31/ExpectativaSobrevida*(1+(IdadeTotal+((TCTotalDias/360)*0,31))/100)
```

b) Formato:
```
0.0000
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.8. **IdadeTotal** (B16)

a) Fórmulas:
```
=DAYS360(DataNascimento;DIB)/360
```

b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.9. **IndiceTeto** (B30)

a) Fórmulas:
```
=MAX(BaseIndiceTeto/TetoDDA;1)
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.10. **LinhaInicialTabelaIndices** (B5)

a) Fórmulas:
```
=MATCH(CompetenciaInicial;IndicesConsolidados!A:A;0)
```

b) Formato:
```
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.11. **LinhaInicialTabelaModificadores** (B6)

a) Fórmulas:
```
=MATCH(CompetenciaInicial;CompetenciaModificadores;0)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.12. **LinhaInicialTabelaSalarios** (B7)

a) Fórmulas:
```
=MATCH(CompetenciaInicial;CalculoSalarios!A:A;0)
```

b) Formato:
```
0
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.13. **MediaComFatorPrevidenciario** (B21)

a) Fórmulas:
```
=((MediaSemFatorPrevidenciario*FatorPrevidenciario*AplicacaoProgressivaFatorPrevidenciario)/60)+((MediaSemFatorPrevidenciario*(60-AplicacaoProgressivaFatorPrevidenciario))/60)
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.14. **MediaSemFatorPrevidenciario** (B20)

a) Fórmulas:
```
=IF(AtividadeSecundaria="Sim";(SomaSalarios/DivisorConsiderado)*NumeradorAtividadeSecundaria/DenominadorAtividadeSecundaria;(SomaSalarios/DivisorConsiderado)+ValorAtividadeSecundaria)
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.15. **PBCMaximo** (B11)

a) Fórmulas:
```
=IF(MID(CriterioPC;1;1)="3";15;IF(OR(MID(CriterioPC;1;1)="4";MID(CriterioPC;1;1)="5");48;TotalCompetencias))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 2.16. **PCConsiderado** (B13)

a) Fórmulas:
```
=MIN(TotalSalariosDDA;MAX(PCMaximo;DivisorMinimo))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 2.17. **PCMaximo** (B12)

a) Fórmulas:
```
=IF(OR(MID(CriterioPC;1;1)="1";MID(CriterioPC;1;1)="2");ROUNDDOWN(TotalSalariosDDA*0,8);IF(MID(CriterioPC;1;1)="3";12;IF(OR(MID(CriterioPC;1;1)="4";MID(CriterioPC;1;1)="5");36;TotalSalariosDDA)))
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.18. **PisoDDA** (B22)

a) Fórmulas:
```
=INDEX(SalarioMinimo;MATCH(EOMONTH(DDA;-1)+1;IndicesConsolidados!A:A;0))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.19. **RMI** (B28)

a) Fórmulas:
```
=MIN(TetoDDA;MAX(IF(Limitacao12Ultimos="SIM";MIN(SalarioBeneficio*Coeficiente;MediaUltimos12Salarios);SalarioBeneficio*Coeficiente);IF(MID(Especie;1;2)="36";PisoDDA*Coeficiente;PisoDDA)))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.20. **SalarioBeneficio** (B27)

a) Fórmulas:
```
=MIN(TetoDDA;MAX(PisoDDA;IF(OR(MID(CriterioPC;1;1)="4";MID(CriterioPC;1;1)="5");MediaUltimos36SalariosDe48;IF(MID(CriterioPC;1;1)="3";MediaUltimos12SalariosDe15;IF(AplicarFatorPrevidenciario="FACULTATIVO";MAX(MediaComFatorPrevidenciario;MediaSemFatorPrevidenciario);IF(AplicarFatorPrevidenciario="NÃO";MediaSemFatorPrevidenciario;MediaComFatorPrevidenciario))))))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.21. **SomaSalarios** (B19)

a) Fórmulas:
```
=SUM(ARRAYFORMULA(OFFSET(SalarioAtualizado;1;0;TotalCompetencias)*OFFSET(SalarioUtilizado;1;0;TotalCompetencias)))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.22. **TCTotalDias** (B15)

a) Fórmulas:
```
=(TCAnos*360)+(TCMeses*30)+TCDias + (IF(Sexo="Mulher";360*5;0))
```

b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.23. **TetoDDA** (B23)

a) Fórmulas:
```
=INDEX(TetoBeneficio;MATCH(EOMONTH(DDA;-1)+1;IndicesConsolidados!A:A;0))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 2.24. **TotalCompetencias** (B8)

a) Fórmulas:
```
=DATEDIF(CompetenciaInicial;CompetenciaFinal;"M")+1
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 2.25. **TotalSalariosDDA** (B9)

a) Fórmulas:
```
=COUNTIF(SalarioAtualizado;">0")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

## 3. Página "CalculoRMI"

### 3.1. **AdmiteZero** (H:H)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(AdmiteZero)=1;"Admite Zero?";IF(ROW(AdmiteZero)<=TotalCompetencias+1;UPPER(OFFSET(ModificadoresUsarPiso;LinhaInicialTabelaModificadores-2;0;TotalCompetencias+1))<>"SIM";"")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.2. **Competencia** (A:A)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(Competencia)=1;"Competência";IF(ROW(Competencia)<=TotalCompetencias+1;EOMONTH(CompetenciaInicial;ROW(Competencia)-2);"")))
```

b) Formato:
```
mm/yyyy
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.3. **FatorAtualizacao** (M:M)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(FatorAtualizacao)=1;"Fator Atualização";IF(ROW(FatorAtualizacao)<=TotalCompetencias+1;jef_INDICE_ACUMULADO(OFFSET(IndiceMensalAtualizacao;0;0;TotalCompetencias+1));"")))
```

b) Formato:
```
0.0000000000
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.4. **IndiceMensalAtualizacao** (J:J)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(IndiceMensalAtualizacao)=1;"Índice Mensal";IF(ROW(IndiceMensalAtualizacao)<=TotalCompetencias+1;IF(ISNUMBER(IndiceMensalAtualizacaoModificado);IndiceMensalAtualizacaoModificado;OFFSET(IndiceSalarios;LinhaInicialTabelaIndices-2;0;TotalCompetencias+1));"")))
```

b) Formato:
```
0.0000000000
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.5. **IndiceMensalAtualizacaoAjustado** (L:L)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(IndiceMensalAtualizacaoAjustado)=1;"Índice Ajustado";IF(ROW(IndiceMensalAtualizacaoAjustado)<=TotalCompetencias+1;OFFSET(AjusteMoeda;LinhaInicialTabelaIndices-2;0;TotalCompetencias+1)*OFFSET(IndiceMensalAtualizacao;0;0;TotalCompetencias+1);"")))
```

b) Formato:
```
0.0000000000
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.6. **IndiceMensalAtualizacaoModificado** (K:K)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(IndiceMensalAtualizacaoModificado)=1;"Modificador";IF(ROW(IndiceMensalAtualizacaoModificado)<=TotalCompetencias+1;OFFSET(ModificadoresIndiceMensalAtualizacao;LinhaInicialTabelaModificadores-2;0;TotalCompetencias+1);"")))
```

b) Formato:
```
0.0000000000
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.7. **IndiceModificado** (K:K)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(IndiceMensalAtualizacaoModificado)=1;"Modificador";IF(ROW(IndiceMensalAtualizacaoModificado)<=TotalCompetencias+1;OFFSET(ModificadoresIndiceMensalAtualizacao;LinhaInicialTabelaModificadores-2;0;TotalCompetencias+1);"")))
```

b) Formato:
```
0.0000000000
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.8. **Piso** (B:B)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(Piso)=1;"Piso";IF(ROW(Piso)<=TotalCompetencias+1;IF(ISNUMBER(PisoModificado);PisoModificado;OFFSET(SalarioMinimo;LinhaInicialTabelaIndices-2;0;TotalCompetencias+1));"")))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.9. **PisoModificado** (C:C)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(PisoModificado)=1;"Modificador";IF(ROW(PisoModificado)<=TotalCompetencias+1;OFFSET(ModificadoresPiso;LinhaInicialTabelaModificadores-2;0;TotalCompetencias+1);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.10. **SalarioAjustado** (I:I)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(SalarioAjustado)=1;"Salário Ajustado";IF(ROW(SalarioAjustado)<=TotalCompetencias+1;IF(SalarioBruto>0;IF(SalarioBruto>Teto;Teto;SalarioBruto);IF(AdmiteZero;0;Piso));"")))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.11. **SalarioAtualizado** (N:N)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(SalarioAtualizado)=1;"Salário Atualizado";IF(ROW(SalarioAtualizado)<=TotalCompetencias+1;ROUND(SalarioAjustado*FatorAtualizacao;2);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.12. **SalarioBruto** (F:F)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(SalarioBruto)=1;"Salário Bruto";IF(ROW(SalarioBruto)<=(TotalCompetencias+1);IF(ISNUMBER(SalarioBrutoModificado);SalarioBrutoModificado;OFFSET(ResultadoSalariosFornecidos;LinhaInicialTabelaSalarios-2;0;TotalCompetencias+1));"")))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.13. **SalarioBrutoModificado** (G:G)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(SalarioBrutoModificado)=1;"Modificador";IF(ROW(SalarioBrutoModificado)<=TotalCompetencias+1;OFFSET(ModificadoresSalarios;LinhaInicialTabelaModificadores-2;0;TotalCompetencias+1);"")))
```

b) Formato:
```
0.00
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.14. **SalarioUtilizado** (O:O)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(SalarioUtilizado)=1;"Salários Utilizados";IF(ROW(SalarioUtilizado)<=TotalCompetencias+1;IF(OR(MID(CriterioPC;1;1)="1";MID(CriterioPC;1;1)="2");IF(ISNUMBER(SalarioAtualizado);IF(SalarioAtualizado>0; SalarioAtualizado>=LARGE(SalarioAtualizado;PCConsiderado);FALSE);"");2);"")))
```

b) Formato: padrão  
c) Regras de validação: não há  
d) Notas: não há  

### 3.15. **Teto** (D:D)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(Teto)=1;"Teto";IF(ROW(Teto)<=TotalCompetencias+1;IF(ISNUMBER(TetoModificado);TetoModificado;OFFSET(TetoBeneficio;LinhaInicialTabelaIndices-2;0;TotalCompetencias+1));"")))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

### 3.16. **TetoModificado** (E:E)

a) Fórmulas:
```
=ARRAYFORMULA(IF(ROW(TetoModificado)=1;"Modificador";IF(ROW(TetoModificado)<=TotalCompetencias+1;OFFSET(ModificadoresTeto;LinhaInicialTabelaModificadores-2;0;TotalCompetencias+1);"")))
```

b) Formato:
```
#,##0.00;(#,##0.00)[Red];-
```

c) Regras de validação: não há  
d) Notas: não há  

## 4. Página "ParametrosDemonstrativos"

### 4.1. **DadosObrigatoriosFaltantes** (A23)

a) Fórmulas:
```
=IF(ISNUMBER(Especie);"";"Espécie#")& IF(ISNUMBER(DIB);"";"DIB#")&IF(ISNUMBER(Coeficiente);"";"Coeficiente#")

```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.2. **ModeloSumulaBeneficio** (D2)

a) Fórmulas: não há  
b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.3. **TextoObservacoes** (A12)

a) Fórmulas:
```
=IF(MostrarObservacoesAutomaticas="Sim";IF(ISTEXT(CONCATENATE(TextoObservacoesModificadores));"Modificadores:"&CHAR(10)&CONCATENATE(TextoObservacoesModificadores)&CHAR(10)&CHAR(10);"");"")&IF(ISTEXT(CONCATENATE(ObservacoesFinais));"Observações finais:"&CHAR(10)&ObservacoesFinais;"")
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.4. **TextoObservacoesModificadores** (A2)

a) Fórmulas:
```
=JOIN(CHAR(10);FILTER(OFFSET(ModificadoresObservacoes;5;0);OFFSET(ModificadoresObservacoes;5;0)<>""))
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  

### 4.5. **TextoSumula** (D8)

a) Fórmulas:
```
="DADOS DO BENEFÍCIO:"&CHAR(10)& SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(CONCATENATE(ModeloSumulaBeneficio);"${Especie}";Especie&" - "&INDEX(ListaBeneficios!A:B;MATCH(Especie;ListaBeneficios!A:A;0);2);1);"${RMI}";RMI);"${DIB}";DIB)
```

b) Formato:
```
0.###############
```

c) Regras de validação: não há  
d) Notas: não há  
