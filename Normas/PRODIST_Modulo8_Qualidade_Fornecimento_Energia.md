# PRODIST - Módulo 8: Qualidade do Fornecimento de Energia Elétrica

## Informações do Documento

| Campo | Valor |
|-------|-------|
| **Tipo** | Norma Regulatória |
| **Órgão** | ANEEL - Agência Nacional de Energia Elétrica |
| **Documento** | Anexo VIII da Resolução Normativa nº 956, de 7 de dezembro de 2021 |
| **Módulo** | 8 - Qualidade do Fornecimento de Energia Elétrica |
| **Aplicação** | Sistema Elétrico Nacional |

---

## Índice

1. [Introdução](#seção-80---introdução)
2. [Qualidade do Produto](#seção-81---qualidade-do-produto)
3. [Variações de Tensão em Regime Permanente](#variações-de-tensão-em-regime-permanente)
4. [Fator de Potência](#fator-de-potência)
5. [Distorções Harmônicas](#distorções-harmônicas)
6. [Desequilíbrio de Tensão](#desequilíbrio-de-tensão)
7. [Flutuação de Tensão](#flutuação-de-tensão)
8. [Variação de Frequência](#variação-de-frequência)
9. [Variação de Tensão de Curta Duração (VTCD)](#variação-de-tensão-de-curta-duração--vtcd)

---

## Seção 8.0 - Introdução

### Estrutura do Módulo

Este módulo está estruturado da seguinte forma:

- **Seção 8.1 – Qualidade do produto**: define a terminologia, caracteriza os fenômenos, estabelece os indicadores e limites ou valores de referência, além de definir a metodologia de medição e a gestão das reclamações relativas à conformidade de tensão em regime permanente e transitório;

- **Seção 8.2 – Qualidade do serviço**: define os conjuntos de unidades consumidoras, estabelece as definições, os limites e os procedimentos relativos aos indicadores de continuidade e de atendimento às ocorrências emergenciais, definindo padrões e responsabilidades;

- **Seção 8.3 – Qualidade comercial**: define os procedimentos para a apuração dos indicadores de reclamações, de atendimento telefônico e de cumprimentos dos prazos, e estabelece a metodologia para estabelecimento dos limites do indicador FER;

- **Seção 8.4 – Segurança do trabalho e instalações**: estabelece as condições de acompanhamento da segurança do trabalho e das instalações;

- **Anexos**

### Objetivos

1. Estabelecer os procedimentos relativos à qualidade do fornecimento de energia elétrica na distribuição, no que se refere à qualidade do produto, à qualidade do serviço e à qualidade comercial.

2. Definir os fenômenos relacionados à qualidade do produto, aqui entendidos como aqueles relativos à conformidade da onda de tensão em regime permanente e transitório, estabelecendo seus indicadores, valores de referência, metodologia de medição e gestão das reclamações.

3. Definir fenômenos relacionados à qualidade do serviço, aqui entendidos como aqueles relativos à continuidade do fornecimento de energia elétrica, estabelecendo a metodologia para apuração dos indicadores de continuidade e de atendimento a ocorrências emergenciais, definindo padrões e responsabilidades.

4. Estabelecer os procedimentos relacionados à apuração da qualidade comercial, aqui entendida como sendo a qualidade do atendimento telefônico, do tratamento das reclamações e outras demandas, e do cumprimento dos prazos.

5. Estabelecer os procedimentos para apuração e encaminhamento das informações relativas a acidentes do trabalho e a acidentes com terceiros.

6. Estabelecer os procedimentos para a realização da compensação e o envio dos relatórios de acompanhamento à ANEEL.

### Aplicabilidade

Os procedimentos definidos neste módulo devem ser observados por:

- Consumidores
- Centrais geradoras
- Distribuidoras
- Agentes importadores ou exportadores de energia elétrica
- Transmissoras detentoras de Demais Instalações de Transmissão – DIT
- Operador Nacional do Sistema Elétrico – ONS

---

## Seção 8.1 - Qualidade do Produto

### Caracterização dos Fenômenos

Os seguintes fenômenos associados à qualidade do produto são tratados:

#### Fenômenos de Regime Permanente
1. Variações de tensão em regime permanente
2. Fator de potência
3. Harmônicos
4. Desequilíbrio de tensão
5. Flutuação de tensão
6. Variação de frequência

#### Fenômenos de Regime Transitório
1. Variações de tensão de curta duração – VTCD

---

## Variações de Tensão em Regime Permanente

### Definição

A conformidade de tensão em regime permanente refere-se à comparação do valor de tensão obtido por medição apropriada, no ponto de conexão, em relação aos níveis de tensão especificados como **adequados**, **precários** e **críticos**.

### Classificação da Tensão

Para cada tensão de referência, as leituras classificam-se em três categorias:

| Classificação | Descrição |
|---------------|-----------|
| **Adequada** | Intervalo entre (TR – ΔADINF) e (TR + ΔADSUP) |
| **Precária** | Intervalo entre (TR + ΔADSUP) e (TR + ΔADSUP + ΔPRSUP) ou entre (TR – ΔADINF – ΔPRINF) e (TR – ΔADINF) |
| **Crítica** | Valores acima de (TR + ΔADSUP + ΔPRSUP) ou abaixo de (TR – ΔADINF – ΔPRINF) |

Onde TR = Tensão de Referência

### Indicadores Individuais

#### DRP - Duração Relativa da Transgressão de Tensão Precária

```
DRP = (nlp / 1.008) × 100 [%]
```

#### DRC - Duração Relativa da Transgressão de Tensão Crítica

```
DRC = (nlc / 1.008) × 100 [%]
```

Onde:
- nlp = maior valor entre as fases do número de leituras situadas na faixa precária
- nlc = maior valor entre as fases do número de leituras situadas na faixa crítica

### Limites dos Indicadores

| Indicador | Limite |
|-----------|--------|
| DRP | 3% |
| DRC | 0,5% |

### Indicadores Coletivos

- **ICC** - Índice de Unidades Consumidoras com Tensão Crítica
- **DRPE** - Duração Relativa da Transgressão de Tensão Precária Equivalente
- **DRCE** - Duração Relativa da Transgressão de Tensão Crítica Equivalente

---

## Fator de Potência

### Cálculo

```
fp = P / √(P² + Q²)
```

Ou alternativamente:

```
fp = EA / √(EA² + ER²)
```

Onde:
- fp = fator de potência
- P = potência ativa
- Q = potência reativa
- EA = energia ativa
- ER = energia reativa

### Limites

Para unidade consumidora do Grupo A ou ponto de conexão entre distribuidoras com tensão inferior a 230 kV:

| Tipo | Faixa |
|------|-------|
| Indutivo | 0,92 a 1,00 |
| Capacitivo | 1,00 a 0,92 |

---

## Distorções Harmônicas

### Definição

As distorções harmônicas são fenômenos associados a deformações nas formas de onda das tensões e correntes em relação à onda senoidal da frequência fundamental.

### Indicadores

| Símbolo | Descrição |
|---------|-----------|
| DITh% | Distorção harmônica individual de tensão de ordem h |
| DTT% | Distorção harmônica total de tensão |
| DTTp% | Distorção harmônica total para componentes pares não múltiplas de 3 |
| DTTi% | Distorção harmônica total para componentes ímpares não múltiplas de 3 |
| DTT3% | Distorção harmônica total para componentes múltiplas de 3 |

### Fórmulas de Cálculo

#### Distorção Harmônica Individual (DITh%)

```
DITh% = (Vh / V1) × 100 [%]
```

#### Distorção Harmônica Total (DTT%)

```
DTT% = (√Σ(Vh²) / V1) × 100 [%]
```

Onde h = todas as ordens harmônicas de 2 até hmax

### Limites das Distorções Harmônicas Totais

| Indicador | Vn ≤ 2,3 kV | 2,3 kV < Vn < 69 kV | 69 kV ≤ Vn < 230 kV |
|-----------|-------------|---------------------|---------------------|
| DTT95% | 10,0% | 8,0% | - |
| DTTp95% | 2,5% | 2,0% | - |
| DTTi95% | 7,5% | 6,0% | 4,0% |
| DTT395% | 6,5% | 5,0% | 3,0% |

---

## Desequilíbrio de Tensão

### Definição

O desequilíbrio de tensão é o fenômeno caracterizado por qualquer diferença verificada nas amplitudes entre as três tensões de fase de um determinado sistema trifásico, ou na defasagem elétrica de 120° entre as tensões de fase do mesmo sistema.

### Cálculo do Fator de Desequilíbrio (FD%)

```
FD% = (V- / V+) × 100 [%]
```

Onde:
- V- = magnitude da tensão eficaz de sequência negativa
- V+ = magnitude da tensão eficaz de sequência positiva

### Limites

| Indicador | Vn ≤ 2,3 kV | 2,3 kV < Vn < 230 kV |
|-----------|-------------|----------------------|
| FD95% | 3,0% | 2,0% |

---

## Flutuação de Tensão

### Definição

A flutuação de tensão é um fenômeno caracterizado pela variação aleatória, repetitiva ou esporádica dos valores eficaz ou de pico da tensão instantânea.

### Indicadores

- **Pst**: Severidade dos níveis de cintilação luminosa em período de 10 minutos
- **Plt**: Severidade dos níveis de cintilação luminosa em período de 2 horas
- **Pst95%**: Valor do Pst superado em apenas 5% das 1.008 leituras válidas

### Cálculo do Pst

```
Pst = √(0,0314×P0,1 + 0,0525×P1 + 0,0657×P3 + 0,28×P10 + 0,08×P50)
```

### Cálculo do Plt

```
Plt = ∛((1/12) × Σ(Psti³))
```

### Limites

| Indicador | Vn ≤ 2,3 kV | 2,3 kV < Vn < 69 kV | 69 kV ≤ Vn < 230 kV |
|-----------|-------------|---------------------|---------------------|
| Pst95% | 1,0 pu | 1,5 pu | 2,0 pu |

---

## Variação de Frequência

### Limites em Condições Normais

O sistema de distribuição deve operar dentro dos limites de frequência:

| Condição | Faixa |
|----------|-------|
| Operação normal | 59,9 Hz a 60,1 Hz |
| Após distúrbio (30s) | 59,5 Hz a 60,5 Hz |

### Limites em Condições Extremas

| Condição | Limite |
|----------|--------|
| Máximo absoluto | 66 Hz |
| Mínimo absoluto | 56,5 Hz |
| Acima de 62 Hz | máximo 30 segundos |
| Acima de 63,5 Hz | máximo 10 segundos |
| Abaixo de 58,5 Hz | máximo 10 segundos |
| Abaixo de 57,5 Hz | máximo 5 segundos |

---

## Variação de Tensão de Curta Duração – VTCD

### Definição

Variações de tensão de curta duração são desvios significativos na amplitude do valor eficaz da tensão durante um intervalo de tempo inferior a 3 minutos.

### Classificação das VTCD

| Tipo | Denominação | Duração | Amplitude |
|------|-------------|---------|-----------|
| **Momentânea** | IMT - Interrupção Momentânea | ≤ 3 segundos | < 0,1 pu |
| **Momentânea** | AMT - Afundamento Momentâneo | ≥ 1 ciclo e ≤ 3 segundos | ≥ 0,1 e < 0,9 pu |
| **Momentânea** | EMT - Elevação Momentânea | ≥ 1 ciclo e ≤ 3 segundos | > 1,1 pu |
| **Temporária** | ITT - Interrupção Temporária | > 3 segundos e < 3 minutos | < 0,1 pu |
| **Temporária** | ATT - Afundamento Temporário | > 3 segundos e < 3 minutos | ≥ 0,1 e < 0,9 pu |
| **Temporária** | ETT - Elevação Temporária | > 3 segundos e < 3 minutos | > 1,1 pu |

### Indicadores de VTCD

- **Ve** - Amplitude do evento de VTCD
- **Δte** - Duração do evento de VTCD
- **fe** - Frequência de ocorrência de eventos
- **FI** - Fator de Impacto
- **FIBASE** - Fator de Impacto base

### Cálculo da Amplitude (Ve)

```
Ve = (Vres / Vref) × 100 [%]
```

### Cálculo do Fator de Impacto (FI)

```
FI = Σ(fei × fpondi) / FIBASE
```

### Valor de Referência

O valor de referência do indicador Fator de Impacto para SDMT e SDAT é de **1,0 pu** (período de 30 dias consecutivos).

---

## Compensações

### Cálculo da Compensação por Violação de DRP ou DRC

```
Compensação = [(DRP - DRPlimite)/100 × k1 + (DRC - DRClimite)/100 × k2] × EUSD
```

Onde:
- k1 = 0 se DRP ≤ DRPlimite; k1 = 3 se DRP > DRPlimite
- k2 = 0 se DRC ≤ DRClimite
- k2 = 7 para Baixa Tensão, 5 para Média Tensão, 3 para Alta Tensão (se DRC > DRClimite)
- EUSD = Encargo de Uso do Sistema de Distribuição

---

## Referências

- ANEEL - Agência Nacional de Energia Elétrica
- Resolução Normativa nº 956, de 7 de dezembro de 2021
- PRODIST - Procedimentos de Distribuição de Energia Elétrica no Sistema Elétrico Nacional
