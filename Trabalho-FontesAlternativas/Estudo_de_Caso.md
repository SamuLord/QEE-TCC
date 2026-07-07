# Estudo de Caso: Sistema Fotovoltaico da UnB (Campus Gama - Brasília/DF)

## 1. Proposta do Trabalho

Replicar a metodologia do artigo de referência (comparação PVsyst vs SAM com dados reais) aplicando a um **novo sistema fotovoltaico** localizado em **Brasília-DF**, gerando resultados inéditos.

### Artigo de Referência (Grupo 2)
"Análise Comparativa de Desempenho de um Sistema Fotovoltaico Simulado com as Ferramentas PVsyst e SAM" — IX CBENS, 2022.
- Local: GMU-UNICAMP, Campinas-SP (lat. 22,82°S)
- Potência: 336,96 kWp
- Comparou simulações com 12 meses de dados reais de geração

### Artigo com Dados Reais para o Novo Estudo de Caso
"Evaluation of a Grid-Connected Photovoltaic System at the University of Brasília Based on Brazilian Standard for Performance Monitoring and Analysis"
- Autores: Velasco, L. N.; Francisco, T. M. et al.
- Revista: MDPI Sustainability, v.16, n.24, 11212, 2024
- DOI: 10.3390/su162411212 (open access)
- Link: https://www.mdpi.com/2071-1050/16/24/11212

---

## 2. Por que usar o artigo da UnB?

O artigo da UnB (2024) publicou dados reais de geração mensal de um sistema FV durante 12 meses (Mar/2022 a Fev/2023). Porém, ele **NÃO fez comparação entre softwares de simulação** — ele apenas calculou o PR pela norma ABNT NBR 16274:2014.

**Nossa contribuição inédita:** Pegar esses dados reais de geração e compará-los com as simulações no PVsyst e no SAM, exatamente como o artigo da UNICAMP fez para Campinas. Isso permite:
1. Validar os softwares em uma nova localidade (Brasília vs Campinas)
2. Verificar se o NSRDB é mais preciso em latitudes menores
3. Comparar resultados com clima tropical (Aw) vs subtropical (Cwa)

---

## 3. Especificações do Sistema FV (UnB - Campus Gama)

### Dados Geográficos

| Parâmetro | Valor |
|-----------|-------|
| Local | Campus Gama - FGA/UnB, Brasília-DF |
| Edifício | UED (Unidade de Ensino) |
| Latitude | ~15,86°S |
| Longitude | ~48,05°W |
| Altitude | ~1.100 m |
| Clima (Köppen) | Aw (Tropical com estação seca) |
| Dentro da cobertura NSRDB? | ✅ Sim (limite: 20°S) |

### Módulos Fotovoltaicos — Canadian Solar HiKu CS3W-420P

| Parâmetro | Valor |
|-----------|-------|
| Potência nominal máxima (Pmax) | 420 W |
| Tensão MPPT (Vmpp) | 39,5 V |
| Corrente MPPT (Impp) | 10,64 A |
| Tensão de circuito aberto (Voc) | 48 V |
| Corrente de curto-circuito (Isc) | 11,26 A |
| Eficiência do módulo | 19,01% |
| Temperatura operacional | -40°C a +85°C |
| Coeficiente de temperatura (γ) | -0,37%/°C |
| T_NOCT | 42°C |
| Quantidade total instalada | 298 módulos |

### Inversor 1 — CSI-75K-T400 (usado no subsistema de 74,76 kWp)

| Parâmetro | Valor |
|-----------|-------|
| Potência FV máxima de entrada | 112,5 kW |
| Tensão máxima de entrada CC | 1100 Vdc |
| Tensão de partida CC | 195 Vdc |
| Faixa de tensão MPPT | 180–1000 Vdc |
| Corrente máxima por MPPT (Imp) | 26 A |
| Corrente máxima curto-circuito por MPPT (Isc) | 40 A |
| Potência nominal de saída CA | 75 kW |
| Tensão de saída nominal | 220/380 VCA |
| Corrente nominal de saída | 114 A |
| Eficiência máxima | 98,7% |
| Entradas MPPT | 9 independentes |

### Inversor 2 — CSI-50KTL-GI (usado no subsistema de 50,4 kWp)

| Parâmetro | Valor |
|-----------|-------|
| Potência nominal de saída CA | 50 kW |
| Entradas MPPT | 4 independentes |

### Configuração das Strings (Inversor 1 — CSI-75K-T400)
- Entradas 1, 2, 5, 6: 2 strings em paralelo × 11 módulos em série
- Entradas 3, 4: 2 strings em paralelo × 14 módulos em série
- Entrada 7: 2 strings em paralelo × 12 módulos em série
- Entrada 8: 1 string × 10 módulos

### Configuração das Strings (Inversor 2 — CSI-50KTL-GI)
- Entrada 1: 2 strings em paralelo × 14 módulos
- Entradas 2, 4: 2 strings em paralelo × 12 módulos
- Entrada 3: 3 strings em paralelo × 14 módulos

### Montagem
| Parâmetro | Valor |
|-----------|-------|
| Tipo | Telhado (rooftop) |
| Inclinação | 15° |
| Azimute | 0° (Norte geográfico) |

---

## 4. Subsistema Selecionado para Simulação

### ⚠️ IMPORTANTE: Usaremos o subsistema do INVERSOR 2 (CSI-50KTL-GI)

O inversor 1 (CSI-75K-T400) teve **falhas operacionais** de setembro/2022 a janeiro/2023 (desligamento + strings desconectadas), comprometendo os dados.

O inversor 2 (CSI-50KTL-GI) funcionou **sem falhas durante os 12 meses**, com PR consistente (~0,75 a 0,91).

**Configuração a simular:**
| Parâmetro | Valor |
|-----------|-------|
| Módulos | Canadian Solar CS3W-420P |
| Quantidade | ~120 módulos (50.400 W / 420 W) |
| Potência instalada | 50,4 kWp |
| Inversor | CSI-50KTL-GI (50 kW) |
| Inclinação | 15° |
| Azimute | Norte (0°) |

---

## 5. Dados Reais de Geração — Inversor 2 (CSI-50KTL-GI)

Extraídos da Tabela 2 do artigo da UnB (Sustainability, 2024):

| Mês | E_R,year (kWh) — Geração Real | Irradiância (kWh/m²) | PR_avg |
|-----|-------------------------------|---------------------|--------|
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
| **TOTAL** | **82.900** | **2.020,78** | **0,81 (média)** |

### Figuras de mérito do sistema real:
- **Yf** = 82.900 / 50,4 = **1.644,8 kWh/kWp/ano**
- **PR médio** = **0,81 (81%)**
- **ED** = **82,9 MWh/ano**

---

## 6. Simulações a Realizar

| # | Software | Base de Dados Meteorológicos |
|---|----------|------------------------------|
| 1 | PVsyst | Meteonorm (integrado no PVsyst) |
| 2 | SAM | Meteonorm (exportado do PVsyst em formato SAM CSV) |
| 3 | SAM | NSRDB (download direto pelo SAM) |

---

## 7. Tabela de Resultados (preencher após simulações)

| Mês | Real (kWh) | PVsyst (kWh) | Erro PVsyst | SAM-Met (kWh) | Erro SAM-Met | SAM-NSRDB (kWh) | Erro NSRDB |
|-----|-----------|-------------|-------------|--------------|-------------|----------------|------------|
| Mar/2022 | 7.450 | ___ | ___% | ___ | ___% | ___ | ___% |
| Abr/2022 | 7.560 | ___ | ___% | ___ | ___% | ___ | ___% |
| Mai/2022 | 6.420 | ___ | ___% | ___ | ___% | ___ | ___% |
| Jun/2022 | 6.990 | ___ | ___% | ___ | ___% | ___ | ___% |
| Jul/2022 | 7.520 | ___ | ___% | ___ | ___% | ___ | ___% |
| Ago/2022 | 7.270 | ___ | ___% | ___ | ___% | ___ | ___% |
| Set/2022 | 6.610 | ___ | ___% | ___ | ___% | ___ | ___% |
| Out/2022 | 7.200 | ___ | ___% | ___ | ___% | ___ | ___% |
| Nov/2022 | 5.910 | ___ | ___% | ___ | ___% | ___ | ___% |
| Dez/2022 | 5.540 | ___ | ___% | ___ | ___% | ___ | ___% |
| Jan/2023 | 6.530 | ___ | ___% | ___ | ___% | ___ | ___% |
| Fev/2023 | 6.900 | ___ | ___% | ___ | ___% | ___ | ___% |
| **Total** | **82.900** | **___** | **___%** | **___** | **___%** | **___** | **___%** |

### Fórmula do erro:
```
%Erro = (E_real - E_simulada) / E_real × 100%
```
- Positivo → simulação conservadora (projetou menos que o real)
- Negativo → simulação otimista (projetou mais que o real)

### Limites aceitáveis (Pigueiras, 2005):
- Erro mensal: < ±30%
- Erro anual: < ±10%
