# Estudo de Caso: Estacionamento Solar da UFRJ (Rio de Janeiro-RJ)

## 1. Proposta do Trabalho

Replicar a metodologia do artigo de referência (comparação PVsyst vs SAM com dados reais) aplicando a um **novo sistema fotovoltaico** localizado no **Rio de Janeiro-RJ**, gerando resultados inéditos.

### Artigo de Referência (Grupo 2)
"Análise Comparativa de Desempenho de um Sistema Fotovoltaico Simulado com as Ferramentas PVsyst e SAM" — IX CBENS, 2022.
- Local: GMU-UNICAMP, Campinas-SP (lat. 22,82°S)
- Potência: 336,96 kWp
- Comparou simulações com 12 meses de dados reais de geração

### Fonte dos Dados Reais para o Novo Estudo de Caso
"Análise de Desempenho do Sistema Fotovoltaico Estacionamento Solar da UFRJ"
- Autor: Anderson Victor Videira Dantas
- Monografia (TCC) — Engenharia Elétrica, Escola Politécnica, UFRJ, Julho/2024
- Orientadores: Prof. Amaro Olímpio Pereira Jr., Prof. Marlon Max Huamani Bellido
- Dados disponíveis no Zenodo: https://doi.org/10.5281/zenodo.13334703

---

## 2. Por que usar o Estacionamento Solar da UFRJ?

1. **Potência próxima do artigo original:** 99 kWp (vs 337 kWp da UNICAMP)
2. **12 meses completos de dados sem falhas** (ano 2017)
3. **Sistema bem documentado:** monografia com todos os detalhes técnicos
4. **Latitude muito similar à UNICAMP:** 22,86°S vs 22,82°S — permite comparação direta
5. **Dados públicos:** Google Drive + Zenodo (DOI citável)
6. **6 inversores** — similar ao artigo original (5 inversores)
7. **Clima diferente:** Rio de Janeiro (Af/Am — tropical úmido) vs Campinas (Cwa — subtropical)

---

## 3. Especificações Técnicas do Sistema

### Dados Geográficos

| Parâmetro | Valor |
|-----------|-------|
| Local | Estacionamento do Centro de Tecnologia (CT), Cidade Universitária |
| Universidade | UFRJ — Ilha do Fundão, Rio de Janeiro-RJ |
| Latitude | ~22,86°S |
| Longitude | ~43,23°W |
| Altitude | ~11 m |
| Clima (Köppen) | Af/Am (Tropical úmido) |
| Potência instalada | **99 kWp** |
| Geração estimada | 140 MWh/ano |
| Inauguração | 2016 |
| Tipo de montagem | **Carport** (estacionamento coberto) |
| Inclinação | **10°** |
| Azimute | **46° para Oeste** (NNO) |

### Módulos Fotovoltaicos — Kyocera KD250GH-4FB2

| Parâmetro | Valor |
|-----------|-------|
| Fabricante | Kyocera |
| Modelo | KD250GH-4FB2 |
| Potência máxima (Pmax) | 250 W |
| Tensão de máxima potência (Vmpp) | 29,8 V |
| Corrente de máxima potência (Impp) | 8,39 A |
| Tensão de circuito aberto (Voc) | 36,9 V |
| Corrente de curto-circuito (Isc) | 9,09 A |
| Eficiência | 15,1% |
| Coef. temperatura Voc | -0,36 %/°C |
| Coef. temperatura Isc | +0,06 %/°C |
| Coef. temperatura Pmax | **-0,46 %/°C** |
| Células por módulo | 60 |
| Tecnologia | **Policristalino** |
| Dimensões | 1662 × 990 × 46 mm |
| Quantidade total | **396 módulos** |

### Inversores — Kaco Powador 20TL3

| Parâmetro | Valor |
|-----------|-------|
| Fabricante | Kaco Energy |
| Modelo | Powador 20TL3 |
| Potência nominal CA | **17 kW** |
| Tensão máxima CC | 1000 V |
| Faixa MPPT | **460–800 V** |
| Corrente máxima CC | 2 × 18,6 A |
| Tensão saída CA | 380/220 V |
| Frequência | 60 Hz |
| Corrente máxima CA | 3 × 24,6 A |
| Fator de potência | 0,8 |
| Eficiência máxima | **98%** |
| Quantidade | **6 inversores** |

### Configuração do Array
- **22 arranjos** × 18 módulos em série = **396 módulos** (99 kWp)
- 6 String Boxes distribuem os arranjos para 6 inversores
- Tensão string (18 módulos em série): 18 × 29,8V = **536,4 V** → Faixa MPPT 460–800V ✅

---

## 4. Dados Reais de Geração — Ano 2017

Extraídos da Tabela 5.6 da monografia de Dantas (2024). ECA,d = energia CA média diária.
Total mensal calculado: ECA,d × dias do mês.

| Mês | ECA,d (kWh/dia) | Dias | **Total Mensal (kWh)** | Yf (kWh/kWp/dia) | PR (%) |
|-----|-----------------|------|----------------------|-------------------|--------|
| Janeiro | 483,50 | 31 | **14.989** | 4,88 | 79,4 |
| Fevereiro | 495,10 | 28 | **13.863** | 4,99 | 78,7 |
| Março* | 391,60 | 31 | **12.140** | 3,96 | 78,8 |
| Abril | 328,10 | 30 | **9.843** | 3,31 | 79,7 |
| Maio | 297,80 | 31 | **9.232** | 3,01 | 79,9 |
| Junho | 295,20 | 30 | **8.856** | 2,98 | 79,2 |
| Julho | 338,30 | 31 | **10.487** | 3,42 | 81,3 |
| Agosto | 302,40 | 31 | **9.374** | 3,00 | 83,7 |
| Setembro | 440,10 | 30 | **13.203** | 4,45 | 77,1 |
| Outubro | 400,50 | 31 | **12.416** | 4,05 | 81,1 |
| Novembro | 396,90 | 30 | **11.907** | 4,01 | 78,9 |
| Dezembro | 383,40 | 31 | **11.885** | 3,87 | 75,0 |
| **Total Anual** | **379,40 (média)** | **365** | **~138.195** | **3,83** | **79,5** |

*Março: dados de 2016 (ausentes na tabela 2017)

### Figuras de mérito anuais do sistema real (2017):
- **Yf** = 138.195 / 99 = **1.395,9 kWh/kWp/ano**
- **PR médio** = **79,5%**
- **ED** = **~138,2 MWh/ano**

---

## 5. Simulações a Realizar

| # | Software | Base de Dados Meteorológicos |
|---|----------|------------------------------|
| 1 | PVsyst | Meteonorm (integrado) |
| 2 | SAM | Meteonorm (exportado do PVsyst) |
| 3 | SAM | NSRDB (download direto) |

---

## 6. Tabela de Resultados (preencher após simulações)

| Mês | Real (kWh) | PVsyst (kWh) | Erro PVsyst | SAM-Met (kWh) | Erro SAM-Met | SAM-NSRDB (kWh) | Erro NSRDB |
|-----|-----------|-------------|-------------|--------------|-------------|----------------|------------|
| Jan | 14.989 | ___ | ___% | ___ | ___% | ___ | ___% |
| Fev | 13.863 | ___ | ___% | ___ | ___% | ___ | ___% |
| Mar | 12.140 | ___ | ___% | ___ | ___% | ___ | ___% |
| Abr | 9.843 | ___ | ___% | ___ | ___% | ___ | ___% |
| Mai | 9.232 | ___ | ___% | ___ | ___% | ___ | ___% |
| Jun | 8.856 | ___ | ___% | ___ | ___% | ___ | ___% |
| Jul | 10.487 | ___ | ___% | ___ | ___% | ___ | ___% |
| Ago | 9.374 | ___ | ___% | ___ | ___% | ___ | ___% |
| Set | 13.203 | ___ | ___% | ___ | ___% | ___ | ___% |
| Out | 12.416 | ___ | ___% | ___ | ___% | ___ | ___% |
| Nov | 11.907 | ___ | ___% | ___ | ___% | ___ | ___% |
| Dez | 11.885 | ___ | ___% | ___ | ___% | ___ | ___% |
| **Total** | **~138.195** | **___** | **___%** | **___** | **___%** | **___** | **___%** |

### Fórmula do erro:
```
%Erro = (E_real - E_simulada) / E_real × 100%
```
- Positivo → simulação conservadora (projetou menos que o real)
- Negativo → simulação otimista (projetou mais que o real)

### Limites aceitáveis (Pigueiras, 2005):
- Erro mensal: < ±30%
- Erro anual: < ±10%

---

## 7. Observações sobre o NSRDB

A latitude do Rio de Janeiro (~22,86°S) está no **limite** da cobertura do NSRDB (PSMv3 cobre até 20°S). Porém:
- O artigo original da UNICAMP usou NSRDB para Campinas (22,82°S) com sucesso
- Versões mais recentes do NSRDB (GOES-16/17) cobrem até 60°S
- Testar no SAM: se não conseguir dados TMY para a coordenada exata, ajustar ligeiramente para norte

Se o NSRDB não funcionar para o RJ, a alternativa é usar apenas 2 simulações (PVsyst + SAM com Meteonorm) e discutir essa limitação no artigo.
