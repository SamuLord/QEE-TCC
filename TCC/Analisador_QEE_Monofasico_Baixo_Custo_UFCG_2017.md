# Projeto de um Analisador da Qualidade da Energia Elétrica Monofásico de Baixo Custo

## Informações do Documento

| Campo | Valor |
|-------|-------|
| **Tipo** | Trabalho de Conclusão de Curso (TCC) |
| **Instituição** | Universidade Federal de Campina Grande (UFCG) |
| **Curso** | Graduação em Engenharia Elétrica |
| **Autor** | Aislan Galdino dos Santos |
| **Orientador** | Prof. Célio Anésio da Silva, D.Sc. |
| **Área** | Processamento de Energia |
| **Ano** | 2017 |
| **Local** | Campina Grande - PB |

---

## Índice

1. [Resumo](#resumo)
2. [Introdução](#1-introdução)
3. [Fundamentação Teórica](#2-fundamentação-teórica)
4. [Projeto do Equipamento](#3-projeto-do-equipamento)
5. [Resultados Experimentais](#4-resultados-experimentais)
6. [Conclusão](#5-conclusão)

---

## Resumo

A busca por reduções de custos eleva a cada dia as exigências sobre a quantidade e mais ainda sobre a qualidade daquilo que é consumido. Em especial na avaliação da energia elétrica, seus parâmetros de qualidade além de serem exigências legais são pontos determinantes na economia de energia, que no mercado competitivo que se instaura pode ser um parâmetro decisivo.

O objetivo geral desse trabalho é idealizar e construir um analisador da qualidade da energia de baixo custo microprocessado, utilizando componentes de fácil acesso. O protótipo desenvolvido permitiu a aquisição da tensão, corrente, potências, harmônicos dentre outros parâmetros que são utilizados para a análise da qualidade da energia elétrica.

**Palavras-chave**: Qualidade de energia elétrica, Qualímetro, Harmônicos, Baixa tensão.

---

## Abstract

The quest for cost reductions increases the demands on quantity each day and more on the quality of what is consumed. In particular in the evaluation of electric energy, its quality parameters besides being legal requirements are decisive points in energy saving, which in the competitive market that is established can be a decisive parameter.

The general objective of this work is to idealize and construct a microprocessed low cost energy quality analyzer using easily accessible components. The developed prototype allowed the acquisition of voltage, current, power, harmonics among other parameters that are used to analyze the quality of electric energy.

**Keywords**: Power quality, Power meter, Harmonics, Low voltage.

---

## 1. Introdução

### 1.1 Motivação

Alterações da qualidade de energia afetam os consumidores de energia elétrica de diversas formas, sendo os consumidores de porte industrial os mais afetados, pois uma falta de energia durante poucos segundos obriga a fábrica a reiniciar todo o processo, causando grandes prejuízos financeiros e perda de parte da produção.

Um dispositivo de análise da qualidade da energia é uma ferramenta crucial para o profissional responsável em corrigir e/ou projetar um sistema imune a condições desfavoráveis. O problema de qualidade da energia elétrica é resolvido por análise e não por uma simples medição.

O custo de aquisição de um qualímetro comercial é alto, principalmente para os modelos com mais recursos e certificação para medição de grandes potências. Em alguns casos esse custo alto inviabiliza o estudo da qualidade de energia em instalações de pequena demanda energética.

### 1.2 Objetivos

#### Objetivo Geral
Construir um sistema de baixo custo que faça a leitura de parâmetros relacionados à qualidade da energia elétrica.

#### Especificações
- Aplicação em rede elétrica monofásica
- Tensões de até 230 VRMS
- Cargas de até 15 kVA

#### Funções Propostas
- Medição de tensão instantânea e RMS
- Medição de corrente instantânea e RMS
- Medição de defasagem entre tensão e corrente
- Medição de potência ativa, reativa e aparente
- Medição de frequência e período
- Medição de fator de potência
- Representação em Série de Fourier
- Cálculo da THD (Total Harmonic Distortion)
- Datalogger com armazenamento em cartão SD

---

## 2. Fundamentação Teórica

### 2.1 Qualidade da Energia Elétrica

A qualidade da energia elétrica está relacionada a qualquer problema da tensão, corrente ou frequência que resulta em uma falha ou má operação nos equipamentos dos consumidores.

#### Aspectos Avaliados na QEE
1. Tensão em regime permanente
2. Fator de potência
3. Harmônicos
4. Desequilíbrio de tensão entre fases
5. Flutuação de tensão
6. Variação de frequência

### 2.2 Grandezas Físicas

#### Valores Eficazes (RMS)
Valor equivalente de uma grandeza alternada que produziria o mesmo efeito térmico que uma grandeza contínua.

#### Potência Instantânea
```
p(t) = v(t) × i(t)
```

#### Potência Ativa (P)
Valor médio da potência instantânea em um período completo.
```
P = (1/T) × ∫p(t)dt [W]
```

#### Potência Reativa (Q)
Componente da potência que não realiza trabalho útil.
```
Q = V × I × sen(φ) [VAr]
```

#### Potência Aparente (S)
```
S = V × I [VA]
S² = P² + Q²
```

#### Triângulo de Potências
```
      S (VA)
     /|
    / |
   /  | Q (VAr)
  /φ  |
 /____|
   P (W)
```

### 2.3 Distúrbios Associados à QEE

| Distúrbio | Descrição |
|-----------|-----------|
| **Sobretensões** | Elevação da tensão acima dos limites nominais |
| **VTCD** | Variações de Tensão de Curta Duração |
| **Flutuações** | Variações repetitivas ou aleatórias da tensão |
| **Transitórios** | Variações rápidas e de curta duração |
| **Desequilíbrios** | Diferenças entre as fases de um sistema trifásico |
| **Distorções** | Presença de harmônicos na forma de onda |
| **Variações de Frequência** | Desvios da frequência nominal (60 Hz) |

### 2.4 Harmônicos e THD

A THD (Total Harmonic Distortion) quantifica a distorção total da forma de onda:

```
THD = √(Σ(Vh²)) / V1 × 100%
```

Onde:
- Vh = amplitude da harmônica de ordem h
- V1 = amplitude da fundamental

---

## 3. Projeto do Equipamento

### 3.1 Arquitetura do Sistema

O sistema é composto por duas partes:

1. **Hardware de Aquisição**: Instalado na rede monofásica, monitora tensão e corrente, realiza cálculos e armazena dados em cartão SD.

2. **Software de Análise**: Executa em computador pessoal, lê os dados e apresenta resultados ao usuário.

### 3.2 Recursos Utilizados

#### Arduino Uno
- Microcontrolador ATmega328P
- 14 pinos digitais I/O
- 6 entradas analógicas
- Clock de 16 MHz
- Conversor A/D de 10 bits

#### Sensor de Corrente SCT013-000
- Transformador de corrente não invasivo
- Faixa: 0-100A
- Saída: 0-50mA

#### Cartão SD
- Armazenamento de dados (datalogger)
- Interface SPI

### 3.3 Circuitos Condicionadores

#### Medição de Corrente
- Resistor de carga para conversão corrente-tensão
- Offset de 2,5V para leitura de sinais AC
- Filtro passa-baixa

#### Medição de Tensão
- Divisor resistivo para atenuação
- Offset de 2,5V
- Filtro passa-baixa

#### Medição de Frequência
- Circuito comparador para detecção de cruzamento por zero
- Entrada digital do Arduino para contagem de período

### 3.4 Diagrama de Blocos

```
┌─────────────┐    ┌──────────────┐    ┌─────────────┐
│   Rede AC   │───▶│ Condicionador│───▶│   Arduino   │
│  127/220V   │    │   de Sinal   │    │     Uno     │
└─────────────┘    └──────────────┘    └──────┬──────┘
                                              │
                   ┌──────────────┐           │
                   │  Cartão SD   │◀──────────┤
                   │  (Datalog)   │           │
                   └──────────────┘           │
                                              ▼
                   ┌──────────────┐    ┌─────────────┐
                   │   Análise    │◀───│ Computador  │
                   │   (MATLAB)   │    │   (PC)      │
                   └──────────────┘    └─────────────┘
```

---

## 4. Resultados Experimentais

### 4.1 Testes com Sinais Simulados

Foram realizados testes comparativos entre o protótipo e um osciloscópio de referência utilizando sinais gerados por gerador de funções.

#### Resultados dos Testes

| Teste | Parâmetro | Valor Referência | Valor Medido | Erro |
|-------|-----------|------------------|--------------|------|
| 1 | Tensão RMS | 127V | 126,8V | 0,16% |
| 2 | Corrente RMS | 5A | 4,98A | 0,40% |
| 3 | Frequência | 60Hz | 60,01Hz | 0,02% |
| 4 | Fator de Potência | 0,85 | 0,84 | 1,18% |

### 4.2 Testes com Cargas Reais

Comparação com analisador comercial Nexus 1500+ em quadro de distribuição do Laboratório de Sistemas de Potência (LSP).

#### Resultados Comparativos

| Parâmetro | Nexus 1500+ | Protótipo | Erro Relativo |
|-----------|-------------|-----------|---------------|
| Tensão (V) | 127,3 | 127,1 | 0,16% |
| Corrente (A) | 12,45 | 12,38 | 0,56% |
| Frequência (Hz) | 60,00 | 60,01 | 0,02% |
| Potência Ativa (W) | 1520 | 1508 | 0,79% |
| Potência Reativa (VAr) | 485 | 479 | 1,24% |
| Potência Aparente (VA) | 1595 | 1582 | 0,82% |
| Fator de Potência | 0,953 | 0,951 | 0,21% |

### 4.3 Testes em Eletrodomésticos

#### Liquidificador
- Medição de harmônicos em diferentes velocidades
- THD variando conforme posição da chave

#### Chuveiro Elétrico
| Ajuste | Tensão (V) | Corrente (A) | Potência (W) | FP |
|--------|------------|--------------|--------------|-----|
| Verão | 127 | 22,5 | 2857 | 1,00 |
| Inverno | 127 | 35,2 | 4470 | 1,00 |

### 4.4 Avaliação dos Resultados

Os erros obtidos foram baixos (geralmente < 2%), justificando a aplicação do protótipo em:
- Sistemas didáticos
- Investigação inicial de pequenas cargas
- Monitoramento de baixo custo

---

## 5. Conclusão

O protótipo desenvolvido atendeu aos objetivos propostos, permitindo a aquisição e análise de parâmetros de qualidade de energia elétrica com erros aceitáveis para aplicações didáticas e investigativas.

### Principais Contribuições
- Sistema de baixo custo utilizando Arduino
- Medição de múltiplos parâmetros de QEE
- Armazenamento de dados para análise posterior
- Interface com MATLAB para processamento avançado

### Limitações
- Aplicação apenas monofásica
- Precisão inferior a equipamentos comerciais certificados
- Necessidade de calibração periódica

### Trabalhos Futuros
- Expansão para sistemas trifásicos
- Implementação de comunicação wireless
- Desenvolvimento de interface gráfica dedicada
- Melhoria na precisão dos sensores

---

## Lista de Abreviaturas

| Sigla | Significado |
|-------|-------------|
| ANEEL | Agência Nacional de Energia Elétrica |
| FFT | Fast Fourier Transform |
| IEC | International Electrotechnical Commission |
| IEEE | Institute of Electrical and Electronics Engineers |
| LSP | Laboratório de Sistemas de Potência |
| ONS | Operador Nacional do Sistema |
| PRODIST | Procedimentos de Distribuição de Energia Elétrica |
| QEE | Qualidade da Energia Elétrica |
| RMS | Root Mean Square |
| SD | Secure Disk |
| SIN | Sistema Interligado Nacional |
| THD | Total Harmonic Distortion |
| VTCD | Variações de Tensão de Curta Duração |

---

## Referências

1. PRODIST - Módulo 8: Qualidade da Energia Elétrica. ANEEL, 2017.
2. DECKMANN, S. M.; POMÍLIO, J. A. Avaliação da Qualidade da Energia Elétrica. UNICAMP, 2016.
3. IEEE Std 519-2014: Recommended Practice and Requirements for Harmonic Control in Electric Power Systems.
4. IEC 61000-4-30: Testing and measurement techniques - Power quality measurement methods.
