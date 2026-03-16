# ONS - Submódulo 9.7: Indicadores de Qualidade de Energia Elétrica da Rede Básica

## Informações do Documento

| Campo | Valor |
|-------|-------|
| **Tipo** | Procedimentos de Rede - Indicadores |
| **Órgão** | ONS - Operador Nacional do Sistema Elétrico |
| **Submódulo** | 9.7 |
| **Revisão** | 2020.12 |
| **Vigência** | 01/01/2021 |
| **Base Legal** | Resolução Normativa nº 903/2020 |

---

## Índice

1. [Objetivos](#1-objetivos)
2. [Indicadores de Continuidade do Serviço](#2-indicadores-de-continuidade-do-serviço)
3. [Indicadores de Frequência](#3-indicadores-de-frequência)
4. [Indicadores de Tensão em Regime Permanente](#4-indicadores-de-tensão-em-regime-permanente)
5. [Indicadores de Flutuação, Desequilíbrio e Distorção Harmônica](#5-indicadores-de-flutuação-desequilíbrio-e-distorção-harmônica)
6. [Indicadores de VTCD](#6-indicadores-de-vtcd)

---

## 1. Objetivos

Estabelecer a sistemática para a apuração e a divulgação dos indicadores de desempenho da Rede Básica relacionados à qualidade de energia elétrica (QEE) e apresentar os valores limites de referência, nos aspectos global e individual quanto à QEE.

---

## 2. Indicadores de Continuidade do Serviço

### 2.1 DIPC - Duração da Interrupção do Ponto de Controle

#### Definição
Somatório das durações das interrupções de serviço do ponto de controle, num determinado período de apuração.

#### Agregações
- **Sistêmica**: ponto de controle, agente, estado, região e sistema
- **Espacial**: nível de tensão e tipo de barramento
- **Temporal**: mensal, trimestral, anual e por valores históricos anualizados

#### Divulgação
- Periodicidade: **mensal**
- O ONS calcula, divulga e encaminha à ANEEL por meio de relatório específico

### 2.2 DMIPC - Duração Máxima da Interrupção do Ponto de Controle

#### Definição
Maior duração de interrupção de serviço do ponto de controle, entre aquelas utilizadas no cálculo do indicador DIPC, num determinado período de apuração.

#### Agregações
- **Sistêmica**: ponto de controle, agente, estado, região e sistema
- **Espacial**: nível de tensão e tipo de barramento
- **Temporal**: mensal

#### Divulgação
- Periodicidade: **mensal**

### 2.3 FIPC - Frequência da Interrupção do Ponto de Controle

#### Definição
Frequência (número de vezes) em que ocorreu interrupção de serviço do ponto de controle, num determinado período de apuração.

#### Agregações
- **Sistêmica**: ponto de controle, agente, estado, região e sistema
- **Espacial**: nível de tensão e tipo de barramento
- **Temporal**: mensal, trimestral, anual e por valores históricos anualizados

#### Divulgação
- Periodicidade: **mensal**

---

## 3. Indicadores de Frequência

### 3.1 DFP - Desempenho da Frequência em Regime Permanente

#### Definição
Indicador coletado de forma contínua pelo ONS, com apuração realizada em base diária, que avalia as variações de frequência ocorridas durante a operação do sistema elétrico em regime permanente.

#### Formulação

```
DFP = (1 – (n / 1440)) × 100 (%)
```

Onde:
- n = número de vezes em que a integral do módulo do desvio de frequência (A), calculada para intervalos de 1 minuto, foi superior a 0,1 Hz.min

#### Cálculo da Integral do Desvio

```
A = ∫|Δf(t)|.dt (Hz.min)
```

Onde:
- A = Integral do módulo do desvio da frequência
- Δf = Desvio da frequência: f – f₀
- f = Frequência medida (Hz)
- f₀ = Frequência nominal: 60,00 Hz
- t = Tempo (minutos)

#### Agregações
- **Espacial**: sistema
- **Temporal**: diária, mensal e anual

#### Divulgação
- Periodicidade: **mensal**

### 3.2 DFD - Desempenho da Frequência em Distúrbios

#### Definição
Indicador coletado durante distúrbios, com apuração em base anual, que avalia as variações de frequência ocorridas durante distúrbios no sistema elétrico.

#### Agregações
- **Espacial**: sistema
- **Temporal**: evento, mensal e anual

#### Divulgação
- Periodicidade: **mensal**

---

## 4. Indicadores de Tensão em Regime Permanente

### 4.1 Definições

- **Pontos de observação**: locais onde se localizam o Sistema de Medição para Faturamento (SMF)
- **Tensão de leitura (TL)**: valores de tensão eficaz fase-neutro, integralizados em intervalos de 10 minutos
- **Tensão contratada (TC)**: igual à tensão nominal (TN) para pontos da Rede Básica

### 4.2 Indicadores

#### DRP - Duração Relativa de Violação de Tensão Precária

```
DRPFase (%) = (nlpFase / nFase) × 100
```

#### DRC - Duração Relativa de Violação de Tensão Crítica

```
DRCFase (%) = (nlcFase / nFase) × 100
```

Onde:
- nlpFase = número de leituras da fase com tensão precária (mensal)
- nlcFase = número de leituras da fase com tensão crítica (mensal)
- nFase = número de leituras da fase (mensal)

### 4.3 Classificação da Tensão de Atendimento

| Tensão Nominal (kV) | Adequada | Precária | Crítica |
|---------------------|----------|----------|---------|
| TN ≥ 230 | 0,95 TC ≤ TL ≤ 1,05 TC | 0,93 TC ≤ TL < 0,95 TC ou 1,05 TC < TL ≤ 1,07 TC | TL < 0,93 TC ou TL > 1,07 TC |
| 69 ≤ TN < 230 | 0,95 TC ≤ TL ≤ 1,05 TC | 0,90 TC ≤ TL < 0,95 TC ou 1,05 TC < TL ≤ 1,07 TC | TL < 0,90 TC ou TL > 1,07 TC |
| 1 < TN < 69 | 0,93 TC ≤ TL ≤ 1,05 TC | 0,90 TC ≤ TL < 0,93 TC | TL < 0,90 TC ou TL > 1,05 TC |

### 4.4 Agregações
- **Sistêmica**: ponto de observação, agente de operação conectante, estado, região e sistema
- **Temporal**: mensal e anual

### 4.5 Divulgação
- Periodicidade: **mensal**

---

## 5. Indicadores de Flutuação, Desequilíbrio e Distorção Harmônica

### 5.1 Flutuação de Tensão

#### Definição
Variação aleatória, repetitiva ou esporádica, do valor eficaz da tensão. Relaciona-se com a operação de cargas não lineares que apresentem consumo de potência variável no tempo.

#### Indicadores

**Pst - Indicador de Severidade de Cintilação de Curta Duração**

Representa a severidade dos níveis de cintilação causados pela flutuação de tensão verificada num período contínuo de 10 minutos.

```
Pst = √(0,0314×P₀,₁ + 0,0525×P₁ + 0,0657×P₃ + 0,28×P₁₀ + 0,08×P₅₀)
```

**Plt - Indicador de Severidade de Cintilação de Longa Duração**

Representa a severidade dos níveis de cintilação verificada num período contínuo de 2 horas.

```
Plt = ∛((1/12) × Σ(Psti³))
```

**Indicadores de Referência:**
- **PstD95%**: valor do Pst superado em 5% dos registros obtidos em 24 horas
- **PltS95%**: valor do Plt superado em 5% dos registros obtidos em 7 dias consecutivos

### 5.2 Desequilíbrio de Tensão

#### Definição
Relação entre as componentes da tensão de sequência negativa (V₂) e positiva (V₁).

#### Fórmula

```
K = (V₂ / V₁) × 100 [%]
```

**Indicador de Referência:**
- **KS95%**: maior valor entre os sete valores diários obtidos ao longo de 7 dias consecutivos

### 5.3 Distorção Harmônica de Tensão

#### Definição
Observada por meio de indicadores associados à distorção harmônica de tensão, monitorada em barramentos sob responsabilidade de concessionárias de transmissão.

#### Indicadores

**DTHI - Distorção de Tensão Harmônica Individual**

```
DTHIh = (Vh / V1) × 100 [%]
```

**DTHT - Distorção de Tensão Harmônica Total**

```
DTHT = √(Σ DTHIh²) [%]
```

Onde h = ordens harmônicas de 2 a 50

**Indicador de Referência:**
- **DTHTS95%**: valor superado em 5% dos registros obtidos em 7 dias consecutivos

---

## 6. Indicadores de VTCD

### 6.1 Definição

VTCD (Variação de Tensão de Curta Duração) é um evento aleatório de tensão caracterizado por desvio significativo, por curto intervalo de tempo, do valor eficaz da tensão.

### 6.2 Parâmetros

- **Amplitude**: valor extremo do valor eficaz da tensão, dentre as três fases, enquanto perdurar o evento
- **Duração**: intervalo de tempo decorrido entre o instante em que o valor eficaz ultrapassa determinado limite e o instante em que volta a cruzar esse limite

### 6.3 Classificação das VTCD

| Tipo | Duração | Amplitude (em relação à TN) |
|------|---------|----------------------------|
| **IMT** - Interrupção Momentânea | ≤ 3 segundos | < 0,1 pu |
| **AMT** - Afundamento Momentâneo | ≥ 1 ciclo e ≤ 3 segundos | ≥ 0,1 e < 0,9 pu |
| **EMT** - Elevação Momentânea | ≥ 1 ciclo e ≤ 3 segundos | > 1,1 pu |
| **ITT** - Interrupção Temporária | > 3 segundos e ≤ 1 minuto | < 0,1 pu |
| **ATT** - Afundamento Temporário | > 3 segundos e ≤ 1 minuto | ≥ 0,1 e < 0,9 pu |
| **ETT** - Elevação Temporária | > 3 segundos e ≤ 1 minuto | > 1,1 pu |

### 6.4 Configurações de Disparo

| Tipo de Evento | Início de Gravação | Reinício de Gravação |
|----------------|-------------------|---------------------|
| Afundamento | 0,90 p.u. | 0,92 p.u. |
| Elevação | 1,10 p.u. | 1,08 p.u. |

### 6.5 Agregação de Eventos

- **Agregação de fases**: eventos simultâneos são agregados compondo um mesmo evento
- **Agregação temporal**: eventos consecutivos em período de 1 minuto são agregados em único evento
- **Amplitude após agregação**: mínimo valor para afundamento, máximo valor para elevação

---

## 7. Referências

- ONS - Operador Nacional do Sistema Elétrico
- Procedimentos de Rede - Módulo 9 - Indicadores
- Submódulo 6.15 - Gerenciamento da qualidade da energia elétrica da Rede Básica
- Resolução Normativa nº 903/2020
- IEC 61000-4-15 - Flickermeter – Functional and Design Specifications
