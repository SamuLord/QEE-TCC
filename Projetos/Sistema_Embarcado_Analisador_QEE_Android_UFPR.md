# Sistema Embarcado Analisador de Qualidade de Energia com Interface em Aplicação Android

## Informações do Documento

| Campo | Valor |
|-------|-------|
| **Tipo** | Artigo Técnico / Projeto Acadêmico |
| **Instituição** | Universidade Federal do Paraná (UFPR) |
| **Grupo** | GICS - Grupo de Concepção de Circuitos e Sistemas Integrados |
| **Autores** | Rafael Correa, Caio Molinari, Luis Lolis |
| **Local** | Curitiba, Brasil |
| **Evento** | Seminários de Microeletrônica do Paraná |

---

## Índice

1. [Resumo](#resumo)
2. [Introdução](#1-introdução)
3. [Instrumentação](#2-instrumentação)
4. [Algoritmos](#3-algoritmos)
5. [Conexão e Aplicativo](#4-conexão-e-aplicativo)
6. [Resultados](#5-resultados)
7. [Conclusão](#6-conclusão)

---

## Resumo

Este artigo apresenta um projeto de sistemas eletrônicos embarcados, baseado em microcontrolador ESP-32, capaz de aferir dados de tensão e corrente elétrica da rede e, a partir deles, calcular:
- Distorção harmônica total (DTT)
- Fator de potência (FP)
- Frequência

As métricas são enviadas via Wi-Fi (IEEE 802.11) a um servidor Firebase, do Google, de onde são lidas por uma aplicação desenvolvida para Android e apresentadas ao usuário.

### Características Principais
- Algoritmo desenvolvido em C++
- Aplicação Android construída em Java
- Circuito de instrumentação para aquisição de dados reais
- Custo aproximado: R$ 200,00 (vs. R$ 50.000,00 de medidores comerciais como Fluke 435)

### Resultados
- Erro relativo menor que 1% em todas as métricas
- Envio de dados ao aplicativo funcionando corretamente
- Circuitos de instrumentação com resultados conforme esperado

---

## 1. Introdução

A grande maioria dos equipamentos eletrônicos da atualidade é alimentada por fontes comutadas, responsáveis por injetar grande quantidade de corrente harmônica no sistema, gerando tensões harmônicas. Tais distorções são prejudiciais para os equipamentos conectados à rede, podendo causar consideráveis impactos econômicos.

### Objetivo
Desenvolver um sistema embarcado de baixo custo capaz de realizar medidas de qualidade de energia cumprindo a legislação sobre medidores (PRODIST - Módulo 8).

### Aplicação
Melhorar a eficiência energética de pequenas e médias empresas.

---

## 2. Instrumentação

### 2.1 Especificações do CAD

O CAD interno do microcontrolador ESP-32 tem faixa de tensão de entrada recomendada:
- **Mínimo**: 100 mV
- **Máximo**: 950 mV

### 2.2 Circuito de Aferição de Tensão

#### Amplificador Diferencial
Projetado para aferir sinal de tensão alternada da rede elétrica com valor máximo de 220 VRMS.

**Equação de Ganho:**
```
VOUT = (R5/R4) × VIN
```

**Faixa de Saída Projetada (para 220 VRMS):**
- Tensão mínima: 125 mV
- Tensão máxima: 955 mV

### 2.3 Circuito de Aferição de Corrente

#### Sensor de Efeito Hall ACS712
- Faixa de operação: ±5 A
- Sensibilidade: 185 mV/A
- Conexão: em série com o ramo a ser analisado

**Faixa de Saída Projetada (para 5 A de pico):**
- Tensão mínima: 384 mV
- Tensão máxima: 897 mV

### 2.4 Filtro Anti-Aliasing

#### Filtro Biquadrático Tow-Thomas
- Tipo: Passa-baixa
- Frequência de corte: 2 kHz (30ª harmônica de 60 Hz)
- Objetivo: Atenuar componentes de alta frequência

**Equação de Ganho:**
```
VOUT = (R8/R7) × VIN
```

### 2.5 Fonte de Alimentação

#### Fonte Simétrica
- Tensões geradas: ±5,4 V e 12 V
- Componentes: divisor de tensão, buffer com amplificador operacional, capacitores de bypass
- Conversor Boost MT3608 para geração de 12 V

---

## 3. Algoritmos

### 3.1 Transformada Rápida de Fourier (FFT)

#### Parâmetros de Amostragem
- Número de amostras: 512
- Frequência de amostragem: 3840 Hz (período de 260 µs)
- Harmônicas analisadas: até a 30ª (1800 Hz)
- Critério de Nyquist: respeitado (fs > 2 × fmax)

### 3.2 Cálculo da Distorção Harmônica Total (DTT)

Conforme método definido pelo PRODIST - Módulo 8:

```
DTT% = (√Σ(Vh²) / V1) × 100
```

Onde:
- V1 = amplitude da tensão RMS da harmônica fundamental
- Vh = amplitude da h-ésima ordem harmônica

### 3.3 Cálculo do Fator de Potência (FP)

Desenvolvido a partir da FFT dos sinais de entrada:

```
FP = cos[arctan(Vi(f)/Vr(f)) - arctan(Ii(f)/Ir(f))]
```

Onde:
- i = valores imaginários da FFT
- r = valores reais da FFT
- f = frequência fundamental (60 Hz)

### 3.4 Cálculo da Frequência

#### Método: Interpolação Linear nos Cruzamentos por Zero

1. Remoção da componente DC do sinal de tensão
2. Detecção de cruzamentos por zero usando interpolação linear
3. Cálculo do período médio entre cruzamentos
4. Conversão para frequência

#### Parâmetros de Amostragem para Frequência
- Frequência de amostragem: 384 Hz
- Número de amostras: 512
- Múltiplo da frequência principal (3840 Hz / 10 = 384 Hz)

---

## 4. Conexão e Aplicativo

### 4.1 Arquitetura do Sistema

```
┌─────────────┐     Wi-Fi      ┌─────────────┐     Internet    ┌─────────────┐
│   ESP-32    │───────────────▶│   Firebase  │◀───────────────▶│  Aplicativo │
│ (Medidor)   │   IEEE 802.11  │   (Google)  │                 │   Android   │
└─────────────┘                └─────────────┘                 └─────────────┘
```

### 4.2 Servidor Firebase

- Serviço em cloud do Google
- Dados armazenados em formato de árvore
- Envio periódico de informações ao aplicativo

### 4.3 Aplicativo Android

#### Tecnologias
- Linguagem: Java
- Framework: Android Studio

#### Funcionalidades
- Menu de cadastro e login de usuário
- Visualização de métricas em tempo real
- Histórico de 24 horas

#### Interfaces Gráficas
1. **Tela de Tempo Real**: Exibe DTT, FP e Frequência atuais
2. **Tela de Histórico**: Gráficos das últimas 24 horas

### 4.4 Taxa de Atualização

- Aproximadamente 10 segundos
- Variação de ±5 segundos dependendo da velocidade da conexão Wi-Fi

---

## 5. Resultados

### 5.1 Validação do Circuito de Tensão

| Parâmetro | Valor de Entrada | Saída Esperada | Saída Medida |
|-----------|------------------|----------------|--------------|
| Amplitude | 4,5 V (equiv. 220 VRMS) | 112-944 mV | 112-944 mV ✓ |

### 5.2 Validação do Circuito de Corrente

| Parâmetro | Valor de Entrada | Saída Esperada | Saída Medida |
|-----------|------------------|----------------|--------------|
| Corrente | 900 mA (carga 200W) | 598-684 mV | 591-673 mV ✓ |

### 5.3 Validação do Filtro Anti-Aliasing

- Frequência de corte medida: **1800 Hz** ✓
- Adequado para análise até a 30ª harmônica

### 5.4 Resultados de DTT

| Forma de Onda (60 Hz) | DTT Teórica | DTT Medida (Gerador) | DTT Medida (Simulado) | Erro |
|-----------------------|-------------|----------------------|-----------------------|------|
| Senoidal | 0% | 0,97% | 0% | 0,97% |
| Quadrada | 48,3% | 48,24% | 48,24% | 0,06% |

### 5.5 Resultados de Frequência

| Frequência de Entrada | Medida (Gerador) | Medida (Simulado) | Erro Relativo |
|-----------------------|------------------|-------------------|---------------|
| 58 Hz | 58,00 Hz | 58,00 Hz | 0% |
| 60 Hz | 60,00 Hz | 60,00 Hz | 0% |
| 62 Hz | 62,00 Hz | 62,00 Hz | 0% |

### 5.6 Resultados de Fator de Potência

| Defasagem | FP Teórico | FP Medido (Gerador) | FP Medido (Simulado) | Erro |
|-----------|------------|---------------------|----------------------|------|
| 0° | 1,000 | 1,000 | 1,000 | 0% |
| 140° | 0,766 | 0,762 | 0,766 | 0,52% |
| 120° | 0,500 | 0,501 | 0,500 | 0,20% |

---

## 6. Conclusão

O projeto teve sucesso dentro do proposto:
- ✓ Cálculo de todas as métricas com precisão necessária
- ✓ Interface adequada com o usuário via aplicativo Android
- ✓ Custo significativamente menor que medidores comerciais
- ✓ Aplicável a empresas de pequeno ou médio porte

### Trabalhos Futuros

1. Implementação do cálculo de valor eficaz e potência ativa
2. Criação de site web como alternativa ao aplicativo
3. Testes comparativos com medidor Fluke para validação da DTT
4. Expansão para sistemas trifásicos

---

## Comparativo de Custos

| Equipamento | Custo Aproximado |
|-------------|------------------|
| Protótipo desenvolvido | R$ 200,00 |
| Fluke 435 Series II | R$ 50.000,00 |
| **Economia** | **99,6%** |

---

## Referências

1. RODRIGUES, A. M. Influência da distorção harmônica e de desequilíbrios em medidores de energia elétrica ativa. UFPR, 2009.

2. POMILIO, J. A. Harmônicos e Fator de Potência: um Curso de Extensão. UNICAMP, 1997.

3. MOLINARI, C. Sistema embarcado medidor de taxa de distorção harmônica e fator de potência da rede. 2020.

4. MORAIS, J. ESP32 – Analisando e corrigindo o ADC interno. Embarcados.

5. MALIK, B. AC Voltage measurement using PIC16F877A microcontroller.

6. OPPENHEIM, A. V. Processamento em Tempo Discreto de Sinais. 3ª Edição. Pearson Education, 2012.

7. ANTUNES, P. R. Plataforma de aquisição de dados e algoritmo não embarcado para medição de distorção harmônica na rede elétrica. UFPR, 2016.

8. NATIONAL INSTRUMENTS. Understanding FFTs and Windowing.

9. ANEEL. PRODIST Módulo 8 – Qualidade da Energia Elétrica, 2016.
