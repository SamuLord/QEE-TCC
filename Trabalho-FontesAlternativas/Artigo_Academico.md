# ANÁLISE COMPARATIVA DE DESEMPENHO DE UM SISTEMA FOTOVOLTAICO SIMULADO COM AS FERRAMENTAS PVSYST E SAM: ESTUDO DE CASO NO RIO DE JANEIRO

**Autores:** [Nomes dos integrantes do grupo]  
**Disciplina:** Fontes Alternativas de Energias  
**Instituição:** [Nome da universidade]

---

## RESUMO

Este trabalho propõe realizar uma análise comparativa entre os softwares de simulação fotovoltaica PVsyst e System Advisor Model (SAM), aplicando a metodologia a um sistema de 99 kWp instalado no Estacionamento Solar do Centro de Tecnologia da Universidade Federal do Rio de Janeiro (UFRJ). Foram realizadas três simulações: PVsyst com Meteonorm, SAM com Meteonorm e SAM com NSRDB. Os resultados simulados foram comparados com dados reais de geração mensal ao longo de 12 meses (2017), obtidos a partir do monitoramento do sistema publicado por Dantas (2024). Utilizaram-se como indicadores a Produtividade Final (Yf), o Performance Ratio (PR) e a Energia Entregue (ED), além do erro percentual mensal e anual. O objetivo é verificar se as conclusões de um estudo anterior, realizado para um sistema em Campinas-SP, se mantêm para uma localidade com características climáticas distintas no Rio de Janeiro.

**Palavras-chave:** Software Fotovoltaico, System Advisor Model, PVsyst, Simulação Fotovoltaica, Performance Ratio, Rio de Janeiro.

---

## 1. INTRODUÇÃO

A energia solar fotovoltaica consolidou-se como uma das principais fontes de energia renovável no cenário mundial. O Brasil atingiu a marca de 50 GW de capacidade solar instalada em novembro de 2024, posicionando-se como o 6º maior país em capacidade fotovoltaica do mundo (ABSOLAR, 2024). Esse crescimento expressivo foi impulsionado pela regulamentação da geração distribuída por meio da Resolução Normativa 482/2012 da ANEEL, que permitiu a injeção de excedentes na rede elétrica, e pela subsequente Lei nº 14.300/2022, que estabeleceu o marco legal da microgeração e minigeração distribuída (ANEEL, 2012).

Para viabilizar economicamente os projetos fotovoltaicos, a previsão precisa de geração de energia é fundamental. Nesse contexto, softwares de simulação fotovoltaica são amplamente utilizados como ferramentas de dimensionamento e análise, pois permitem considerar fatores complexos como perdas ôhmicas, sombreamento, efeito da temperatura, posicionamento geográfico e variações climáticas. A precisão desses softwares depende tanto dos modelos matemáticos empregados quanto da qualidade dos bancos de dados meteorológicos utilizados (Oliveira, 2017).

Dentre os softwares disponíveis, o PVsyst é considerado referência no ambiente acadêmico e comercial, sendo largamente utilizado por projetistas em todo o mundo. O System Advisor Model (SAM), desenvolvido pelo National Renewable Energy Laboratory (NREL) dos Estados Unidos, destaca-se por ser gratuito e de código aberto, tornando-se uma alternativa acessível para a comunidade acadêmica (SAM, 2024).

Silva et al. (2022) realizaram uma análise comparativa entre o PVsyst e o SAM para um sistema de 336,96 kWp instalado no Ginásio Multidisciplinar da UNICAMP (Campinas-SP), comparando três simulações com dados reais de 12 meses. Os resultados mostraram que o SAM com NSRDB foi o mais otimista (erro de -1,21%), o SAM com Meteonorm o mais conservador (+11,18%) e o PVsyst apresentou erro intermediário de +6,36%. Entretanto, essas conclusões foram obtidas exclusivamente para a região de Campinas-SP (latitude 22,82°S, clima subtropical — Cwa).

O presente trabalho tem como objetivo replicar essa metodologia para um sistema fotovoltaico de 99 kWp instalado no Estacionamento Solar do Centro de Tecnologia da UFRJ, no Rio de Janeiro-RJ (latitude 22,86°S, clima tropical úmido — Af/Am). Os dados reais de geração foram obtidos a partir da monografia de Dantas (2024), que monitorou o sistema durante o período de 2016 a 2019. As contribuições deste trabalho são:

1. Validar os softwares PVsyst e SAM para um sistema no Rio de Janeiro;
2. Verificar se o comportamento otimista/conservador dos softwares se mantém em clima tropical marítimo;
3. Avaliar a influência dos bancos de dados meteorológicos (Meteonorm vs NSRDB) na precisão das estimativas;
4. Comparar os resultados obtidos com as conclusões do estudo de Campinas.

---

## 2. REVISÃO BIBLIOGRÁFICA

### 2.1 System Advisor Model (SAM)

O System Advisor Model é um software gratuito e de código aberto desenvolvido pelo NREL. Permite modelar e simular sistemas fotovoltaicos conectados à rede, autônomos e com armazenamento. Suas principais vantagens incluem: banco de dados atualizado de componentes, integração com Python via SAM SDK, compatibilidade nativa com o banco de dados NSRDB, e capacidade de simulação de sistemas com baterias (BESS). A interface é menos intuitiva que softwares comerciais, podendo limitar seu uso para projetistas iniciantes (SAM, 2024).

### 2.2 PVsyst

O PVsyst é um software comercial de dimensionamento e simulação FV amplamente reconhecido no mercado. Oferece recursos como modelagem 3D, análise de sombreamento detalhada, importação de arquivos CAD, diagramas de curva I×V, verificação de compatibilidade módulo-inversor e relatórios detalhados com diagrama de perdas. O banco de dados meteorológico predominante é o Meteonorm. A principal desvantagem é o custo de licença, embora ofereça versão trial (PVsyst, 2024).

### 2.3 Bancos de Dados Meteorológicos

**Meteonorm:** Banco de dados meteorológicos com mais de 8.000 estações e cinco satélites geoestacionários, cobertura global, resolução horária e algoritmos de interpolação sofisticados. É compatível com os principais softwares de simulação FV (Meteonorm, 2024).

**NSRDB (National Solar Radiation Database):** Desenvolvido pelo NREL, fornece dados de radiação solar derivados de satélites geoestacionários com resolução de 30 min e 4 km. A cobertura para as Américas estende-se de 60°S a 60°N (versão GOES-16/17). Inclui GHI, DNI, DHI, temperatura e velocidade do vento (NREL, 2024).

### 2.4 Figuras de Mérito

As figuras de mérito são indicadores normalizados que permitem comparar o desempenho de sistemas FV independentemente do tamanho e localização (Almeida, 2012; IEC 61724, 1998).

**Produtividade Final (Yf):**

$$Y_f = \frac{E_{CA}}{P_{instalada}} \quad \text{[kWh/kWp]}$$

**Performance Ratio (PR):**

$$PR = \frac{Y_f}{Y_r} \quad \text{[adimensional]}$$

Onde $Y_r = H_t / G_{ref}$ (rendimento de referência), $H_t$ é a irradiação no plano do módulo e $G_{ref}$ = 1 kW/m².

**Erro Percentual:**

$$\%Erro = \frac{E_{real} - E_{simulada}}{E_{real}} \times 100\%$$

Limites aceitáveis (Pigueiras, 2005): ±30% mensal; ±10% anual.

### 2.5 Trabalhos Relacionados

- Machado et al. (2020): PVsyst, PV*SOL, Helioscope — 22,95 kWp, UNICAMP. Erros < 4%.
- Silva et al. (2020): Homer, PV*SOL, PVsyst — 336,96 kWp, GMU/UNICAMP.
- Silva et al. (2022): PVsyst e SAM — 336,96 kWp, GMU/UNICAMP. SAM-NSRDB mais otimista, SAM-Meteonorm mais conservador.
- Dantas (2024): Análise de desempenho do Estacionamento Solar da UFRJ (99 kWp), PR médio 79,5% (2017). Dados disponíveis no Zenodo.

---

## 3. METODOLOGIA

### 3.1 Sistema Fotovoltaico de Referência

O sistema utilizado é o Estacionamento Solar do Centro de Tecnologia da UFRJ, inaugurado em 2016 no âmbito do Programa Fundo Verde. Consiste em uma estrutura de carport com painéis fotovoltaicos instalados sobre vagas de estacionamento na Ilha do Fundão, Rio de Janeiro-RJ.

**Tabela 1.** Especificações do sistema fotovoltaico.

| Parâmetro | Valor |
|-----------|-------|
| Localização | CT-UFRJ, Ilha do Fundão, RJ |
| Latitude / Longitude | 22,86°S / 43,23°W |
| Altitude | ~11 m |
| Clima (Köppen) | Af/Am (Tropical úmido) |
| Potência instalada | **99 kWp** |
| Módulos | Kyocera KD250GH-4FB2 (250 Wp, policristalino) |
| Quantidade de módulos | 396 (22 arranjos × 18 em série) |
| Inversores | Kaco Powador 20TL3 (17 kW, 98% eficiência) |
| Quantidade de inversores | 6 |
| Inclinação | 10° |
| Azimute | 46° para Oeste (NNO) |
| Tipo de montagem | Carport |

**Tabela 2.** Parâmetros elétricos do módulo Kyocera KD250GH-4FB2.

| Parâmetro | Valor |
|-----------|-------|
| Pmax | 250 W |
| Vmpp | 29,8 V |
| Impp | 8,39 A |
| Voc | 36,9 V |
| Isc | 9,09 A |
| Eficiência | 15,1% |
| Coef. temperatura Pmax | -0,46%/°C |

**Tabela 3.** Parâmetros do inversor Kaco Powador 20TL3.

| Parâmetro | Valor |
|-----------|-------|
| Potência nominal CA | 17 kW |
| Faixa MPPT | 460–800 V |
| Corrente máxima CC | 2 × 18,6 A |
| Eficiência máxima | 98% |

### 3.2 Dados Reais de Geração

Os dados reais foram extraídos de Dantas (2024), correspondentes ao ano de 2017 (com março complementado por dados de 2016 por indisponibilidade). A geração foi monitorada por um medidor ION8650A da Schneider, com dados de energia CA acumulados em kWh a cada 15 minutos.

**Tabela 4.** Dados reais de geração mensal do sistema (2017).

| Mês | ECA média diária (kWh/dia) | Total Mensal (kWh) | Yf (kWh/kWp/dia) | PR (%) |
|-----|---------------------------|-------------------|-------------------|--------|
| Janeiro | 483,50 | 14.989 | 4,88 | 79,4 |
| Fevereiro | 495,10 | 13.863 | 4,99 | 78,7 |
| Março* | 391,60 | 12.140 | 3,96 | 78,8 |
| Abril | 328,10 | 9.843 | 3,31 | 79,7 |
| Maio | 297,80 | 9.232 | 3,01 | 79,9 |
| Junho | 295,20 | 8.856 | 2,98 | 79,2 |
| Julho | 338,30 | 10.487 | 3,42 | 81,3 |
| Agosto | 302,40 | 9.374 | 3,00 | 83,7 |
| Setembro | 440,10 | 13.203 | 4,45 | 77,1 |
| Outubro | 400,50 | 12.416 | 4,05 | 81,1 |
| Novembro | 396,90 | 11.907 | 4,01 | 78,9 |
| Dezembro | 383,40 | 11.885 | 3,87 | 75,0 |
| **Total** | **378,30 (média)** | **~138.195** | **3,83** | **79,5** |

*Março: dados de 2016 por indisponibilidade em 2017.  
Fonte: Dantas (2024), Tabelas 5.5 e 5.6.

### 3.3 Simulações Realizadas

**Tabela 5.** Configuração das simulações.

| Simulação | Software | Base de Dados Meteorológicos |
|-----------|----------|------------------------------|
| 1 | PVsyst | Meteonorm |
| 2 | SAM | Meteonorm (exportado do PVsyst) |
| 3 | SAM | NSRDB |

Em todas as simulações, os parâmetros de módulo, inversor, orientação, inclinação e perdas são idênticos, de modo que as diferenças nos resultados sejam atribuídas exclusivamente ao software e/ou ao banco de dados meteorológicos.

### 3.4 Critérios de Avaliação

- Figuras de mérito: Yf, PR e ED
- Erro percentual mensal e anual em relação aos dados reais
- Classificação: otimista (erro negativo) ou conservadora (erro positivo)
- Limites (Pigueiras, 2005): mensal < ±30%, anual < ±10%

---

## 4. RESULTADOS E DISCUSSÕES

### 4.1 Figuras de Mérito Anuais

**Tabela 6.** Resultados anuais comparados ao sistema real.

| Software | Yf (kWh/kWp/ano) | PR (%) | ED (kWh) |
|----------|------------------|--------|----------|
| **Real (UFRJ)** | **1.395,9** | **79,5** | **138.195** |
| PVsyst (Meteonorm) | ___ | ___ | ___ |
| SAM (Meteonorm) | ___ | ___ | ___ |
| SAM (NSRDB) | ___ | ___ | ___ |

### 4.2 Comparação Mensal

**Tabela 7.** Comparação mensal: geração real vs simulações.

| Mês | Real (kWh) | PVsyst (kWh) | Erro (%) | SAM-Met (kWh) | Erro (%) | SAM-NSRDB (kWh) | Erro (%) |
|-----|-----------|-------------|----------|--------------|----------|-----------------|----------|
| Jan | 14.989 | ___ | ___ | ___ | ___ | ___ | ___ |
| Fev | 13.863 | ___ | ___ | ___ | ___ | ___ | ___ |
| Mar | 12.140 | ___ | ___ | ___ | ___ | ___ | ___ |
| Abr | 9.843 | ___ | ___ | ___ | ___ | ___ | ___ |
| Mai | 9.232 | ___ | ___ | ___ | ___ | ___ | ___ |
| Jun | 8.856 | ___ | ___ | ___ | ___ | ___ | ___ |
| Jul | 10.487 | ___ | ___ | ___ | ___ | ___ | ___ |
| Ago | 9.374 | ___ | ___ | ___ | ___ | ___ | ___ |
| Set | 13.203 | ___ | ___ | ___ | ___ | ___ | ___ |
| Out | 12.416 | ___ | ___ | ___ | ___ | ___ | ___ |
| Nov | 11.907 | ___ | ___ | ___ | ___ | ___ | ___ |
| Dez | 11.885 | ___ | ___ | ___ | ___ | ___ | ___ |
| **Total** | **138.195** | **___** | **___** | **___** | **___** | **___** | **___** |

### 4.3 Análise dos Resultados

[PREENCHER após simulações — discutir:]
- Qual simulação foi mais otimista? Qual mais conservadora?
- Erros mensais dentro de ±30%?
- Erro anual dentro de ±10%?
- Influência do banco de dados (Meteonorm vs NSRDB)
- Influência do software (PVsyst vs SAM com mesma base)
- Efeito do azimute não-ideal (46° Oeste) na precisão

### 4.4 Comparação com Artigo Original (UNICAMP)

**Tabela 8.** Comparação entre os dois estudos.

| Métrica | UNICAMP — Campinas (2022) | UFRJ — Rio de Janeiro (este trabalho) |
|---------|--------------------------|---------------------------------------|
| Latitude | 22,82°S | 22,86°S |
| Clima (Köppen) | Cwa (subtropical úmido) | Af/Am (tropical marítimo) |
| Potência | 336,96 kWp | 99 kWp |
| Módulos | Canadian CS6K-270P | Kyocera KD250GH-4FB2 |
| Inversores | 5× Ingecon Sun 55 | 6× Kaco Powador 20TL3 |
| Inclinação | N/A | 10° |
| Azimute | N/A | 46° Oeste |
| PR real | ~82% | 79,5% |
| Mais otimista | SAM-NSRDB (-1,21%) | ___ |
| Mais conservador | SAM-Meteonorm (+11,18%) | ___ |
| Erro PVsyst | +6,36% | ___ |
| Erro SAM-Meteonorm | +11,18% | ___ |
| Erro SAM-NSRDB | -1,21% | ___ |

[PREENCHER e discutir:]
- Conclusões se mantêm para o RJ?
- O azimute não-ideal (46° Oeste) é captado corretamente pelos softwares?
- Como o clima tropical úmido (mais nebulosidade/chuva) afeta a precisão?

---

## 5. CONCLUSÃO

[PREENCHER após resultados — pontos a abordar:]

- Resumo dos resultados principais
- Qual software/banco de dados mais adequado para o Rio de Janeiro
- Comparação com conclusões do artigo de Campinas
- Se limites de erro foram respeitados
- Limitações: azimute não-ideal, dados de março complementados, sistema de 2016 com possível degradação em 2017
- Sugestões futuras: testar em mais localidades, incluir análise financeira, usar versões atualizadas dos softwares

---

## REFERÊNCIAS

ABSOLAR. Energia solar atinge 50 GW de capacidade instalada no Brasil. Nov. 2024.

ALMEIDA, M. P. Qualificação de Sistemas Fotovoltaicos Conectados à Rede. Dissertação (Mestrado) — Instituto de Energia e Ambiente, USP, 2012.

ANEEL. Resolução Normativa nº 482/2012. 2012.

DANTAS, A. V. V. Análise de Desempenho do Sistema Fotovoltaico Estacionamento Solar da UFRJ. Projeto de Graduação — Escola Politécnica, UFRJ, 2024.

DANTAS, A. V. V. Dados de Operação do Sistema Fotovoltaico Estacionamento Solar da UFRJ de 2016-2019. Zenodo, 2024. DOI: 10.5281/zenodo.13334703.

IEC 61724:1998. Photovoltaic system performance monitoring — Guidelines for measurement, data exchange and analysis.

MACHADO, G. et al. Análise de desempenho de um sistema fotovoltaico com os softwares PVsyst, PV*SOL e Helioscope. 2020.

METEONORM. Meteotest AG. Disponível em: https://meteonorm.com/. 2024.

NREL. National Solar Radiation Database (NSRDB). Disponível em: https://nsrdb.nrel.gov/. 2024.

OLIVEIRA, R. Dimensionamento de sistemas fotovoltaicos: fatores de influência. 2017.

PIGUEIRAS, E. L. C. Caracterización de módulos fotovoltaicos con dispositivo portátil. Tesis Doctoral — UPM, 2005.

PV MAGAZINE. Solar hits 50 GW milestone in Brazil. Nov. 2024.

PVSYST. PVsyst SA. Disponível em: https://www.pvsyst.com/. 2024.

SAM. System Advisor Model. NREL. Disponível em: https://sam.nrel.gov/. 2024.

SILVA, G. A. et al. Análise Comparativa de Desempenho de um Sistema Fotovoltaico Simulado com as Ferramentas PVsyst e SAM. IX CBENS, 2022.

SILVA, J. et al. Análise comparativa de softwares de simulação fotovoltaica para o GMU-UNICAMP. 2020.

---

## FIGURAS A INCLUIR

1. **Foto do Estacionamento Solar:** Usar imagem da monografia de Dantas (2024), Figura 3.1 — citar fonte
2. **Gráfico comparativo mensal:** Criar no Excel (4 séries: Real, PVsyst, SAM-Met, SAM-NSRDB)
3. **Gráfico de erro percentual:** Linhas + referência ±30%
4. **Diagrama de perdas:** Exportar do PVsyst

---

## ⚠️ NOTAS PARA O GRUPO

**Pronto (seções 1, 2, 3):** Introdução, revisão, metodologia com dados reais.

**Falta (após simulações):** Preencher tabelas 6, 7, 8 + seções 4.3, 4.4 e 5.

**Lembrete:** Reescreva com suas palavras antes de entregar. Os resultados devem vir das suas simulações reais.
