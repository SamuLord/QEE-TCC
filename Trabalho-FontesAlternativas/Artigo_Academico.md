# ANÁLISE COMPARATIVA DE DESEMPENHO DE UM SISTEMA FOTOVOLTAICO SIMULADO COM AS FERRAMENTAS PVSYST E SAM: ESTUDO DE CASO EM BRASÍLIA-DF

**Autores:** [Nomes dos integrantes do grupo]  
**Disciplina:** Fontes Alternativas de Energias  
**Instituição:** [Nome da universidade]

---

## RESUMO

Este trabalho propõe realizar uma análise comparativa entre os softwares de simulação fotovoltaica PVsyst e System Advisor Model (SAM), aplicando a metodologia a um sistema de 50,4 kWp instalado na Universidade de Brasília (UnB), Campus Gama. Foram realizadas três simulações: PVsyst com Meteonorm, SAM com Meteonorm e SAM com NSRDB. Os resultados simulados foram comparados com dados reais de geração mensal ao longo de 12 meses (março/2022 a fevereiro/2023), obtidos a partir do monitoramento do sistema publicado por Velasco et al. (2024). Como indicadores de desempenho, foram utilizados a Produtividade Final (Yf), o Performance Ratio (Pr) e a Energia Entregue (ED), além do erro percentual mensal e anual. O objetivo é verificar se as conclusões do estudo de referência, realizado para um sistema em Campinas-SP, se mantêm para uma localidade de menor latitude e clima tropical com estação seca.

**Palavras-chave:** Software Fotovoltaico, System Advisor Model, PVsyst, Simulação Fotovoltaica, Brasília, Performance Ratio.

---

## 1. INTRODUÇÃO

O setor de energia solar fotovoltaica (FV) no Brasil apresentou um crescimento expressivo nos últimos anos. Em novembro de 2024, o país atingiu a marca de 50 GW de capacidade instalada em energia solar, sendo aproximadamente 33,5 GW provenientes de geração distribuída e 16,5 GW de usinas de grande porte, consolidando o Brasil como o 6º maior país em capacidade solar instalada no mundo (ABSOLAR, 2024; PV Magazine, 2024). Esse avanço foi impulsionado pela Resolução Normativa 482/2012 da ANEEL, que regulamentou a microgeração e minigeração distribuída, permitindo a injeção de excedentes na rede elétrica (ANEEL, 2012).

Para viabilizar economicamente os projetos fotovoltaicos, é fundamental que a previsão de geração de energia seja precisa. Nesse contexto, softwares de simulação fotovoltaica são amplamente utilizados como ferramentas de dimensionamento e análise de desempenho, pois consideram fatores como perdas ôhmicas, sombreamento, temperatura de operação, posicionamento geográfico e variações climáticas. A precisão desses softwares depende tanto dos modelos matemáticos empregados quanto da qualidade dos bancos de dados meteorológicos utilizados (Oliveira, 2017; Rosa, 2014).

Dentre os softwares disponíveis no mercado, o PVsyst é considerado uma referência no ambiente acadêmico e comercial, sendo amplamente utilizado por projetistas. Por outro lado, o System Advisor Model (SAM), desenvolvido pelo Laboratório Nacional de Energias Renováveis dos Estados Unidos (NREL), destaca-se por ser gratuito e de código aberto, tornando-se acessível para a comunidade acadêmica e para o mercado (SAM, 2021).

Trabalhos anteriores já realizaram estudos comparativos entre softwares de simulação FV. Machado et al. (2020) compararam PVsyst, PV*SOL e Helioscope para um sistema de 22,95 kWp na UNICAMP, obtendo erros percentuais médios inferiores a 4%. Silva et al. (2020) utilizaram Homer, PV*SOL e PVsyst para simular o sistema de 336,96 kWp do Ginásio Multidisciplinar da UNICAMP (GMU). Mais recentemente, Silva et al. (2022) realizaram a primeira comparação direta entre PVsyst e SAM para o mesmo sistema do GMU, comparando três simulações com dados reais de 12 meses de geração. Os resultados mostraram que o SAM com NSRDB foi o mais otimista (erro de -1,21%), o SAM com Meteonorm o mais conservador (+11,18%) e o PVsyst apresentou erro intermediário de +6,36%.

Entretanto, esses estudos foram realizados exclusivamente na região de Campinas-SP (latitude 22,82°S, clima subtropical úmido — Cwa). Não há na literatura trabalhos que verifiquem se essas conclusões se mantêm para outras regiões do Brasil com características climáticas e geográficas distintas.

Dessa forma, o presente trabalho tem como objetivo replicar a metodologia proposta por Silva et al. (2022), aplicando-a a um sistema fotovoltaico de 50,4 kWp instalado no Campus Gama da Universidade de Brasília (UnB), localizado em Brasília-DF (latitude 15,86°S, clima tropical com estação seca — Aw). Os dados reais de geração foram obtidos a partir do trabalho de Velasco et al. (2024), que monitorou o sistema durante 12 meses. A contribuição deste trabalho consiste em:

1. Validar os softwares PVsyst e SAM para uma nova localidade com clima e latitude distintos;
2. Verificar se o banco de dados NSRDB apresenta melhor desempenho em latitudes mais baixas (mais próximas do equador);
3. Comparar os resultados obtidos com as conclusões do estudo original realizado em Campinas.

---

## 2. REVISÃO BIBLIOGRÁFICA

### 2.1 System Advisor Model (SAM)

O System Advisor Model é um software desenvolvido pelo Laboratório Nacional de Energias Renováveis (NREL) dos Estados Unidos. Trata-se de uma ferramenta gratuita e de código aberto que permite modelar e simular sistemas de energia renovável, incluindo sistemas fotovoltaicos conectados à rede, autônomos e com armazenamento de energia em baterias (SAM, 2021).

Entre as principais vantagens do SAM estão: custo zero de licença; banco de dados atualizado de módulos e inversores; possibilidade de simulação com múltiplos inversores e MPPT; integração com a linguagem Python por meio do SAM SDK; e compatibilidade nativa com o banco de dados meteorológicos NSRDB. Como desvantagem, a interface é menos intuitiva que outros softwares comerciais, e a necessidade de familiaridade com programação pode limitar seu uso para alguns projetistas.

### 2.2 PVsyst

O PVsyst é um software de dimensionamento e simulação de sistemas fotovoltaicos amplamente utilizado no mercado e na academia (Sharma, 2018). O programa permite especificar a potência desejada, selecionar módulos e inversores de um banco de dados interno extenso, realizar análise de sombreamento 3D, importar arquivos CAD e gerar relatórios detalhados com diagramas de perdas.

O PVsyst apresenta diagramas do comportamento da curva I×V dos arranjos, verifica a compatibilidade módulo-inversor quanto à faixa de MPPT, e permite análise de múltiplas fontes de perdas (sombreamento, sobrecarga, temperatura, cabeamento). A principal desvantagem é ser um software pago, com licenças anuais, embora ofereça versão trial de 30 dias.

### 2.3 Bancos de Dados Meteorológicos

#### 2.3.1 Meteonorm

O Meteonorm é um banco de dados meteorológicos reconhecido como fonte confiável no mercado. Possui dados de mais de 8.000 estações meteorológicas e cinco satélites geoestacionários, com cobertura global. Seus dados são disponibilizados em resolução horária e são compatíveis com os formatos dos principais softwares de simulação FV (Santos, 2020; Meteonorm, 2021). A qualidade dos dados é garantida por algoritmos de interpolação sofisticados que permitem estimar valores para localidades sem estações de medição próximas.

#### 2.3.2 NSRDB (National Solar Radiation Database)

O NSRDB é um banco de dados desenvolvido pelo NREL que fornece dados de radiação solar derivados de satélites geoestacionários, com resolução temporal de 30 minutos e resolução espacial de 4 km (NREL, 2021). Os dados incluem irradiância global horizontal (GHI), direta normal (DNI) e difusa horizontal (DHI), além de temperatura ambiente e velocidade do vento.

A cobertura do NSRDB para a América do Sul estende-se até aproximadamente a latitude 20°S na versão PSMv3, abrangendo regiões como Brasília (15,86°S), Fortaleza, Recife e Salvador. Versões mais recentes utilizando satélites GOES-16/17 ampliam a cobertura até 60°S com resolução de 2 km (NREL, 2021).

### 2.4 Figuras de Mérito para Sistemas Fotovoltaicos

As figuras de mérito são indicadores numéricos utilizados para comparar o desempenho de sistemas fotovoltaicos em diferentes configurações e localidades (Almeida, 2012; Benedito, 2009). As principais figuras utilizadas neste trabalho são:

**Produtividade Final (Yf):** Razão entre a energia elétrica em corrente alternada injetada na rede (ED, em kWh) e a potência nominal do sistema (kWp). Permite comparar sistemas de tamanhos distintos.

$$Y_f = \frac{E_D}{P_{instalada}} \quad \text{[kWh/kWp]}$$

**Performance Ratio (Pr):** Índice adimensional que representa a eficiência global do sistema, normalizando a produtividade em relação à radiação disponível. É considerado o principal fator de qualidade para comparação de sistemas FV (Almeida, 2012; Satsangi, 2018).

$$P_r = \frac{E_D}{E_{D,nominal}} = \frac{Y_f}{Y_r}$$

Onde Yr é o rendimento de referência, dado pela razão entre a irradiação no plano dos módulos (kWh/m²) e a irradiância de referência (1 kW/m²).

**Energia Entregue (ED):** Energia total gerada pelo sistema FV e injetada na rede elétrica em um período específico (kWh ou MWh).

**Erro Percentual:** Indicador de precisão dos softwares em relação à geração real:

$$\%Erro = \frac{E_{D,real} - E_{D,simulada}}{E_{D,real}} \times 100\%$$

Quando o resultado é positivo, a simulação foi conservadora (estimou menos que o real). Quando negativo, a simulação foi otimista (estimou mais que o real). Os limites aceitáveis propostos pela literatura são: ±30% para erro mensal e ±10% para erro anual (Pigueiras, 2005).

---

## 3. METODOLOGIA

### 3.1 Sistema Fotovoltaico de Referência

O sistema fotovoltaico utilizado como referência neste trabalho está instalado no telhado do edifício UED (Unidade de Ensino) do Campus Gama da Faculdade Gama (FGA), Universidade de Brasília, conforme apresentado na Figura 1.

**Figura 1** — Vista aérea do Campus Gama da UnB com o sistema FV instalado no edifício UED (1).  
*Fonte: Velasco et al. (2024) — disponível em https://www.mdpi.com/2071-1050/16/24/11212 (CC BY 4.0)*

> **Nota para o grupo:** Baixar a Figura 1 do artigo de Velasco et al. (2024) no MDPI. O artigo é open access (CC BY 4.0), então podem usar as imagens desde que citem a fonte.

O sistema completo possui 298 módulos Canadian Solar HiKu CS3W-420P (potência total de 125,16 kWp), conectados a dois inversores trifásicos Canadian Solar: o Inversor 1 (CSI-75K-T400, 74,76 kWp) e o Inversor 2 (CSI-50KTL-GI, 50,4 kWp). A Tabela 1 apresenta os parâmetros técnicos dos módulos fotovoltaicos e de ambos os inversores.

**Figura 2** — Inversores CSI-50KTL-GI e CSI-75K-T400 e painel elétrico de conexão.  
*Fonte: Velasco et al. (2024)*

> **Nota para o grupo:** Baixar a Figura 2 do artigo original.

**Tabela 1.** Parâmetros dos módulos fotovoltaicos e dos inversores instalados.

| Parâmetros do Módulo — Canadian Solar CS3W-420P | Valor |
|------------------------------------------------|-------|
| Potência nominal máxima (Pmax) | 420 W |
| Tensão MPPT (Vmpp) | 39,5 V |
| Corrente MPPT (Impp) | 10,64 A |
| Tensão de circuito aberto (Voc) | 48 V |
| Corrente de curto-circuito (Isc) | 11,26 A |
| Eficiência do módulo | 19,01% |
| Coeficiente de temperatura (γ) | -0,37%/°C |
| NOCT | 42°C |
| Temperatura operacional | -40°C a +85°C |

| Parâmetros do Inversor 1 — CSI-75K-T400 | Valor |
|-----------------------------------------|-------|
| Potência fotovoltaica máxima de entrada | 112,5 kW |
| Tensão máxima de entrada CC | 1100 Vdc |
| Tensão de partida CC | 195 Vdc |
| Faixa de tensão MPPT | 180–1000 Vdc |
| Corrente máxima de entrada (Imp) por MPPT | 26 A |
| Corrente máxima de curto-circuito (Isc) por MPPT | 40 A |
| Potência nominal de saída CA | 75 kW |
| Tensão de saída nominal | 220/380 VCA |
| Corrente nominal de saída da rede | 114 A |
| Eficiência máxima | 98,7% |
| Entradas MPPT independentes | 9 |

| Parâmetros do Inversor 2 — CSI-50KTL-GI | Valor |
|-----------------------------------------|-------|
| Potência fotovoltaica máxima de entrada | 58 kW |
| Tensão máxima de entrada CC | 1100 Vdc |
| Tensão de partida CC | 200 Vdc |
| Faixa de tensão MPPT | 439–850 Vdc |
| Corrente máxima de entrada (Imp) por MPPT | 28,5 A |
| Corrente máxima de curto-circuito (Isc) por MPPT | 44,5 A |
| Potência nominal de saída CA | 50 kW |
| Tensão de saída nominal | 380/400 VCA |
| Corrente nominal de saída da rede | 76/72,2 A |
| Eficiência máxima | 98,8% |
| Entradas MPPT independentes | 4 |

### Seleção do Subsistema para Simulação

Durante o período de monitoramento (março/2022 a fevereiro/2023), o Inversor 1 (CSI-75K-T400) apresentou falhas operacionais significativas: desligamento do inversor em meados de setembro/2022 (permanecendo inoperante por aproximadamente 45 dias até a substituição em novembro/2022) e desconexão de strings fotovoltaicas por ativação dos dispositivos de proteção (fusíveis), problema identificado apenas no final de janeiro/2023 (Velasco et al., 2024). Essas ocorrências comprometeram os dados de geração do Inversor 1 entre setembro/2022 e janeiro/2023, tornando-os inadequados para comparação com simulações.

Por outro lado, o Inversor 2 (CSI-50KTL-GI, 50,4 kWp) operou sem falhas durante os 12 meses completos, apresentando Performance Ratio consistente entre 0,75 e 0,91. Portanto, o subsistema do Inversor 2 foi selecionado para a análise comparativa deste trabalho.

| Dados do Subsistema Simulado | Valor |
|-----------------------------|-------|
| Inversor utilizado | CSI-50KTL-GI |
| Quantidade de módulos (subsistema) | ~120 |
| Potência instalada | 50,4 kWp |
| Inclinação | 15° |
| Azimute | 0° (Norte geográfico) |
| Tipo de montagem | Telhado fixo |
| Localização | Campus Gama — UnB, Brasília-DF |
| Latitude / Longitude | 15,86°S / 48,05°W |
| Altitude | ~1.100 m |

### 3.2 Dados Reais de Geração

Os dados reais de geração mensal foram extraídos de Velasco et al. (2024), que monitorou o sistema por meio do sistema de supervisão do inversor fornecido pela Canadian Solar. A Tabela 2 apresenta os valores mensais de energia medida e irradiância no plano dos módulos.

**Tabela 2.** Dados reais de geração e irradiância mensal do subsistema FV (Inversor CSI-50KTL-GI, 50,4 kWp).

| Mês | E_R (kWh) — Geração Real | Irradiância (kWh/m²) | PR médio |
|-----|--------------------------|---------------------|----------|
| Março/2022 | 7.450 | 171,61 | 0,87 |
| Abril/2022 | 7.560 | 182,80 | 0,81 |
| Maio/2022 | 6.420 | 153,25 | 0,84 |
| Junho/2022 | 6.990 | 173,27 | 0,81 |
| Julho/2022 | 7.520 | 196,52 | 0,77 |
| Agosto/2022 | 7.270 | 192,77 | 0,75 |
| Setembro/2022 | 6.610 | 175,82 | 0,75 |
| Outubro/2022 | 7.200 | 158,35 | 0,91 |
| Novembro/2022 | 5.910 | 144,20 | 0,82 |
| Dezembro/2022 | 5.540 | 137,19 | 0,81 |
| Janeiro/2023 | 6.530 | 165,00 | 0,79 |
| Fevereiro/2023 | 6.900 | 170,00 | 0,81 |
| **Total anual** | **82.900** | **2.020,78** | **0,81** |

*Fonte: Adaptado de Velasco et al. (2024), Tabela 2.*

### 3.3 Simulações Realizadas

Foram realizadas três simulações, conforme a Tabela 3, replicando a estrutura metodológica de Silva et al. (2022).

**Tabela 3.** Simulações realizadas conforme software e base de dados meteorológicos.

| Simulação | Software | Base de Dados Meteorológicos |
|-----------|----------|------------------------------|
| 1 | PVsyst | Meteonorm |
| 2 | SAM | Meteonorm (exportado do PVsyst) |
| 3 | SAM | NSRDB |

Em todas as simulações, foram utilizados os mesmos parâmetros de módulo, inversor, orientação, inclinação e perdas do sistema, de modo que as diferenças nos resultados possam ser atribuídas exclusivamente ao software de simulação e/ou ao banco de dados meteorológicos utilizado.

### 3.4 Critérios de Avaliação

Os resultados foram avaliados com base em:
- Figuras de mérito: Yf, Pr e ED;
- Erro percentual mensal e anual em relação aos dados reais;
- Classificação das simulações como otimista ou conservadora;
- Comparação com os resultados do estudo de referência (Campinas-SP).

Os limites de aceitabilidade adotados seguem Pigueiras (2005):
- Erro mensal: inferior a ±30%;
- Erro anual médio: inferior a ±10%.

---

## 4. RESULTADOS E DISCUSSÕES

### 4.1 Figuras de Mérito Anuais

**Tabela 4.** Resultados anuais das simulações comparados com o sistema real.

| Software | Yf (kWh/kWp) | Pr (%) | ED (kWh) |
|----------|--------------|--------|----------|
| **Real (UnB)** | **1.644,8** | **81** | **82.900** |
| PVsyst (Meteonorm) | ___ | ___ | ___ |
| SAM (Meteonorm) | ___ | ___ | ___ |
| SAM (NSRDB) | ___ | ___ | ___ |

### 4.2 Comparação Mensal — Simulações vs Geração Real

**Tabela 5.** Comparação mensal entre dados reais e simulações.

| Mês | Real (kWh) | PVsyst (kWh) | Erro (%) | SAM-Met (kWh) | Erro (%) | SAM-NSRDB (kWh) | Erro (%) |
|-----|-----------|-------------|----------|--------------|----------|-----------------|----------|
| Mar/2022 | 7.450 | ___ | ___ | ___ | ___ | ___ | ___ |
| Abr/2022 | 7.560 | ___ | ___ | ___ | ___ | ___ | ___ |
| Mai/2022 | 6.420 | ___ | ___ | ___ | ___ | ___ | ___ |
| Jun/2022 | 6.990 | ___ | ___ | ___ | ___ | ___ | ___ |
| Jul/2022 | 7.520 | ___ | ___ | ___ | ___ | ___ | ___ |
| Ago/2022 | 7.270 | ___ | ___ | ___ | ___ | ___ | ___ |
| Set/2022 | 6.610 | ___ | ___ | ___ | ___ | ___ | ___ |
| Out/2022 | 7.200 | ___ | ___ | ___ | ___ | ___ | ___ |
| Nov/2022 | 5.910 | ___ | ___ | ___ | ___ | ___ | ___ |
| Dez/2022 | 5.540 | ___ | ___ | ___ | ___ | ___ | ___ |
| Jan/2023 | 6.530 | ___ | ___ | ___ | ___ | ___ | ___ |
| Fev/2023 | 6.900 | ___ | ___ | ___ | ___ | ___ | ___ |
| **Total** | **82.900** | **___** | **___** | **___** | **___** | **___** | **___** |

### 4.3 Análise dos Resultados

[PREENCHER após simulações — discutir:]
- Qual simulação foi mais otimista (erro negativo)?
- Qual foi mais conservadora (erro positivo)?
- Os erros mensais ficaram dentro de ±30%?
- O erro anual ficou dentro de ±10%?
- Influência do banco de dados: diferença entre SAM-Meteonorm e SAM-NSRDB
- Influência do software: diferença entre PVsyst e SAM com mesma base

### 4.4 Comparação com o Estudo de Referência (UNICAMP, Campinas-SP)

**Tabela 6.** Comparação dos resultados entre os dois estudos.

| Métrica | UNICAMP — Campinas (2022) | UnB — Brasília (este trabalho) |
|---------|--------------------------|-------------------------------|
| Latitude | 22,82°S | 15,86°S |
| Clima (Köppen) | Cwa (subtropical úmido) | Aw (tropical, estação seca) |
| Potência | 336,96 kWp | 50,4 kWp |
| Simulação mais otimista | SAM-NSRDB (-1,21%) | ___ |
| Simulação mais conservadora | SAM-Meteonorm (+11,18%) | ___ |
| Erro anual PVsyst | +6,36% | ___ |
| Erro anual SAM-Meteonorm | +11,18% | ___ |
| Erro anual SAM-NSRDB | -1,21% | ___ |
| Dentro do limite ±10%? | PVsyst e SAM-NSRDB sim; SAM-Met não | ___ |

[PREENCHER — discutir:]
- As conclusões do artigo original se mantêm?
- O comportamento otimista/conservador dos softwares é o mesmo?
- A latitude/clima influencia na precisão?
- O NSRDB é mais preciso em Brasília por estar mais próximo do equador?

---

## 5. CONCLUSÃO

[PREENCHER após obter resultados — abordar:]

- Resumo dos resultados principais
- Qual software/banco de dados melhor para Brasília
- Comparação com conclusões do artigo de referência
- Se os limites de erro da literatura foram respeitados
- Limitações: dados reais de terceiros, período de 1 ano apenas, apenas 1 subsistema
- Sugestões futuras: testar em mais localidades, usar dados de mais de 1 ano, incluir análise financeira

---

## REFERÊNCIAS

ABSOLAR. Energia solar atinge 50 GW de capacidade instalada no Brasil. Nov. 2024.

ALMEIDA, M. P. Qualificação de Sistemas Fotovoltaicos Conectados à Rede. Dissertação (Mestrado) — Instituto de Energia e Ambiente, USP, 2012.

ANEEL. Resolução Normativa nº 482/2012. Condições gerais para acesso de micro e minigeração distribuída. 2012.

BENEDITO, R. S. Caracterização da geração distribuída de eletricidade por meio de sistemas fotovoltaicos conectados à rede. Dissertação — USP, 2009.

MACHADO, G. et al. Análise de desempenho de um sistema fotovoltaico com os softwares PVsyst, PV*SOL e Helioscope. 2020.

METEONORM. Meteotest AG. Disponível em: https://meteonorm.com/. Acesso em 2024.

NREL. National Solar Radiation Database (NSRDB). Disponível em: https://nsrdb.nrel.gov/. 2021.

OLIVEIRA, R. Dimensionamento de sistemas fotovoltaicos: fatores de influência. 2017.

PIGUEIRAS, E. L. C. Caracterización de módulos fotovoltaicos con dispositivo portátil. Tesis Doctoral — Universidad Politécnica de Madrid, 2005.

PV MAGAZINE. Solar hits 50 GW milestone in Brazil. Nov. 2024. Disponível em: https://www.pv-magazine.com/2024/11/27/solar-hits-50-gw-milestone-in-brazil/

ROSA, L. F. Validação de softwares de simulação fotovoltaica. 2014.

SAM. System Advisor Model. NREL. Disponível em: https://sam.nrel.gov/. 2021.

SANTOS, I. P. Análise comparativa de dados meteorológicos para simulação fotovoltaica. 2020.

SATSANGI, A. Performance analysis of grid-connected solar photovoltaic system. Energy Reports, 2018.

SHARMA, V. PVsyst tutorial and review. 2018.

SILVA, G. A. et al. Análise Comparativa de Desempenho de um Sistema Fotovoltaico Simulado com as Ferramentas PVsyst e SAM. IX Congresso Brasileiro de Energia Solar, 2022.

SILVA, J. et al. Análise comparativa de softwares de simulação fotovoltaica para o GMU-UNICAMP. 2020.

VELASCO, L. N.; FRANCISCO, T. M. et al. Evaluation of a Grid-Connected Photovoltaic System at the University of Brasília Based on Brazilian Standard for Performance Monitoring and Analysis. Sustainability, v.16, n.24, 11212, 2024. DOI: 10.3390/su162411212.

---

## FIGURAS A INCLUIR

### Onde obter as imagens:

1. **Figuras 1 e 2** (sistema FV da UnB): Baixar do artigo de Velasco et al. (2024) em https://www.mdpi.com/2071-1050/16/24/11212
   - O artigo é **open access (CC BY 4.0)** — podem usar desde que citem:
   - "Fonte: Velasco et al. (2024), Sustainability, CC BY 4.0"

2. **Gráfico comparativo de geração mensal** (Figura 3): Vocês criam no Excel após simulações
   - Gráfico de barras: Real vs PVsyst vs SAM-Met vs SAM-NSRDB

3. **Gráfico de erro percentual mensal** (Figura 4): Vocês criam no Excel
   - Gráfico de linhas com 3 séries + linhas de referência ±30%

4. **Comparação com artigo original** (Figura/Tabela 6): Já está na seção 4.4

---

## ⚠️ NOTAS PARA O GRUPO

**O que está PRONTO (seções 1, 2, 3):**
- Introdução escrita
- Revisão bibliográfica completa
- Metodologia detalhada com tabelas de dados reais

**O que FALTA (depende das simulações):**
- Seção 4: preencher tabelas 4, 5, 6 com resultados
- Seção 4.3 e 4.4: escrever análise
- Seção 5: conclusão

**IMPORTANTE:**
- Reescrevam as seções 1-3 com suas palavras antes de entregar
- Não entreguem o texto exatamente como está — adaptem ao estilo de vocês
- As imagens do artigo da UnB podem ser usadas com citação da fonte (CC BY 4.0)
- Os resultados DEVEM ser das simulações que vocês rodarem
