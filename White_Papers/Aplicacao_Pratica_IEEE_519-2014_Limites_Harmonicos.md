# Uma Forma Prática e Eficaz de Aplicar os Limites de Harmônicos da IEEE Std 519-2014

## Informações do Documento

| Campo | Valor |
|-------|-------|
| **Tipo** | White Paper Técnico |
| **Empresas** | STULZ / Mirus International |
| **Autor** | Anthony (Tony) Hoevenaars, BESc'79 |
| **Cargo** | Presidente e CEO da Mirus International |
| **Norma Referenciada** | IEEE Std 519-2014 |
| **Idioma Original** | Inglês |

---

## Índice

1. [Introdução](#introdução)
2. [Limites de Harmônicos da IEEE Std 519-2014](#limites-de-harmônicos-da-ieee-std-519-2014)
3. [Definições Importantes](#definições-importantes)
4. [Por que iTDD faz sentido](#por-que-itdd-faz-sentido)
5. [Como Aplicar a IEEE Std 519](#como-aplicar-a-ieee-std-519)
6. [Equipamentos para Conformidade](#equipamentos-para-conformidade)
7. [Especificação Recomendada](#especificação-recomendada)
8. [Estudo de Caso: Sistema HVAC Hospitalar](#estudo-de-caso-sistema-hvac-hospitalar)

---

## Introdução

A maioria dos engenheiros elétricos hoje reconhece a necessidade de controlar harmônicos em suas redes de distribuição de energia. Se não controlados, os harmônicos podem causar:
- Superaquecimento de equipamentos elétricos
- Problemas operacionais devido a alta distorção de tensão

Associações de normas elétricas como IEEE e IEC introduziram padrões e recomendações que abordam harmônicos, mas nem sempre são fáceis de interpretar ou aplicar.

Este documento foi preparado para auxiliar na aplicação da norma **IEEE Std 519-2014** - "Recommended Practice and Requirements for Harmonic Control in Electrical Power Systems" (Prática Recomendada e Requisitos para Controle de Harmônicos em Sistemas de Energia Elétrica).

---

## Limites de Harmônicos da IEEE Std 519-2014

A última revisão da IEEE Std 519 foi lançada em março de 2014, substituindo a versão anterior de 1992. A norma foi estabelecida para prevenir que harmônicos gerados por cargas não lineares afetem negativamente o sistema de energia e as cargas conectadas.

### Responsabilidades

A norma reconhece:
- **Responsabilidade do usuário**: Não degradar a qualidade da tensão da concessionária ao drenar correntes não lineares ou distorcidas
- **Responsabilidade da concessionária**: Fornecer aos usuários uma tensão próxima à senoidal

### Tabela 1: Limites de Distorção de Tensão

| Tensão do Barramento (V) no PCC | Harmônico Individual (%) | THD Total (%) |
|--------------------------------|--------------------------|---------------|
| V ≤ 1,0 kV | 5,0 | 8,0 |
| 1 kV < V ≤ 69 kV | 3,0 | 5,0 |
| 69 kV < V ≤ 161 kV | 1,5 | 2,5 |
| 161 kV < V | 1,0 | 1,5 |

### Tabela 2: Limites de Distorção de Corrente (120V a 69kV)

| ISC/IL | 3≤h<11 | 11≤h<17 | 17≤h<23 | 23≤h<35 | 35≤h≤50 | TDD |
|--------|--------|---------|---------|---------|---------|-----|
| < 20 | 4,0 | 2,0 | 1,5 | 0,6 | 0,3 | 5,0 |
| 20 < 50 | 7,0 | 3,5 | 2,5 | 1,0 | 0,5 | 8,0 |
| 50 < 100 | 10,0 | 4,5 | 4,0 | 1,5 | 0,7 | 12,0 |
| 100 < 1000 | 12,0 | 5,5 | 5,0 | 2,0 | 1,0 | 15,0 |
| > 1000 | 15,0 | 7,0 | 6,0 | 2,5 | 1,4 | 20,0 |

### Principais Mudanças da Versão 2014

1. Definições de THD e TDD agora permitem inclusão de harmônicos acima da 50ª ordem quando necessário
2. Limites de distorção de tensão para sistemas < 1kV foram relaxados de 5% para 8%
3. Limites mais baixos para Aplicações Especiais e limites mais altos para sistemas dedicados foram removidos
4. Limites de distorção de corrente para sistemas > 161kV foram alterados
5. Limites de Muito Curta Duração e Curta Duração foram introduzidos
6. Permissão para limites harmônicos aumentados em frequências mais altas quando medidas são tomadas para reduzir harmônicos de baixa frequência

---

## Definições Importantes

### PCC - Ponto de Acoplamento Comum

Ponto em um sistema de fornecimento público de energia, eletricamente mais próximo de uma carga específica, no qual outras cargas estão, ou poderiam estar, conectadas. O PCC é um ponto localizado a montante da instalação considerada.

**Uso**: Define a localização onde os limites de harmônicos devem ser aplicados.

### THD - Distorção Harmônica Total

Razão entre a raiz quadrada média da corrente harmônica, considerando componentes harmônicos até a 50ª ordem (excluindo inter-harmônicos), expressa como porcentagem da fundamental.

#### Fórmulas de Cálculo

**Para Corrente (iTHD):**
```
iTHD = √(I₂² + I₃² + I₄² + I₅² + ...) / I₁ × 100%
```

**Para Tensão (vTHD):**
```
vTHD = √(V₂² + V₃² + V₄² + V₅² + ...) / V₁ × 100%
```

### TDD - Distorção de Demanda Total

Razão entre a raiz quadrada média da corrente harmônica, considerando componentes harmônicos até a 50ª ordem, expressa como porcentagem da **corrente de demanda máxima**.

#### Fórmula de Cálculo

```
TDD = √(I₂² + I₃² + I₄² + I₅² + ...) / IL × 100%
```

### IL - Corrente de Demanda Máxima

Valor de corrente no PCC tomado como a soma das correntes correspondentes à demanda máxima durante cada um dos 12 meses anteriores, dividido por 12.

**Problema**: Esta definição é extremamente difícil de aplicar na fase de projeto.

### SCR - Razão de Curto-Circuito (ISC/IL)

Em uma localização específica, a razão entre a corrente de curto-circuito disponível (em amperes) e a corrente de carga (em amperes).

**Importância**: 
- Fornece referência à impedância da fonte relativa à carga
- Quanto maior o SCR, mais relaxados são os limites de distorção de corrente
- Mesma quantidade de harmônicos de corrente produz diferentes níveis de distorção de tensão dependendo da impedância da fonte

---

## Por que iTDD faz sentido

### O Problema com iTHD

O iTHD fornece uma medida relativa do conteúdo harmônico de corrente no nível de carga medido. Porém, pode ser enganoso em condições de carga leve:

- iTHD será quase certamente **maior** em cargas leves do que em cargas pesadas
- Mas as correntes harmônicas reais (em amperes) serão **menores**
- É o valor em amperes que contribui para problemas como superaquecimento e distorção de tensão

### Exemplo Prático: VSD de 350 HP

| Carga | Sem Filtro | Com Filtro |
|-------|------------|------------|
| | 5ª Harm (A) | iTHD | 5ª Harm (A) | iTHD |
| 100% | 110 A | 36% | 5,0 A | 4,2% |
| 75% | 83 A | 37% | 4,8 A | 5,2% |
| 50% | 67 A | 44% | 3,5 A | 6,1% |
| 30% | 48 A | 55% | 2,8 A | 7,8% |
| 25% | 55 A | 77% | 2,4 A | 8,7% |

**Observação**: A 25% de carga, o iTHD mais que dobrou (de 36% para 77%), mas a corrente harmônica real caiu pela metade (de 110A para 55A).

### Conclusão

Usar iTHD em qualquer nível de carga como fator determinante para necessidade de mitigação harmônica seria um erro. O iTDD resolve este problema ao referenciar a corrente de demanda máxima.

---

## Como Aplicar a IEEE Std 519

### Desafios da Aplicação como Norma de Sistema

A IEEE Std 519 foi projetada para ser usada como norma de sistema, mas isso provou ser difícil porque:

1. Requer simulação computacional extensiva
2. Necessita diagrama unifilar detalhado com tipos de carga, tamanhos de cabos e comprimentos
3. Localização do PCC deve ser acordada entre concessionária, projetista e usuário final
4. Perfis de carga e piores condições operacionais precisam ser determinados
5. Corrente de demanda máxima (IL) é impossível de determinar sem operar por pelo menos 1 ano

### Solução Prática: Aplicação nos Terminais do Equipamento

Muitos engenheiros determinaram que a forma mais simples de garantir controle efetivo da distorção harmônica é aplicar os limites da norma **individualmente em cada equipamento**.

#### Vantagens
- Insistindo que os limites de corrente harmônica sejam aplicados nos terminais do equipamento não linear, a conformidade em base de sistema pode ser assegurada
- Simplifica a especificação e verificação

#### Erro Comum a Evitar
O erro mais comum é usar **iTHD em vez de iTDD**. Isso quase certamente forçará o fabricante a usar equipamento de mitigação superdimensionado.

### Abordagem Recomendada

1. **Usar iTDD, não iTHD**
2. **Definir corrente de demanda máxima** como a corrente máxima de operação da carga não linear nas condições de projeto
3. **Calcular SCR** para determinar os limites aplicáveis da Tabela 2
4. **Para aplicações críticas**: especificar iTDD < 5% independentemente do SCR

---

## Equipamentos para Conformidade

### Filtro Harmônico Passivo de Espectro Amplo (WSHF)

#### Características do Lineator AUHF
- Conexão em série
- Combinação de elemento de bloqueio e elemento de filtragem sintonizado
- Sintonizado próximo à 4ª harmônica (visto dos terminais de entrada)
- Previne importação de harmônicos do lado da linha

#### Desempenho
- Modelos padrão: iTDD < 8% em carga plena
- Modelos premium: iTDD < 5%

#### Critérios de Projeto Importantes
- Reatância capacitiva em carga leve: < 15% da potência nominal do filtro
- Garante operação estável tanto em fonte de gerador de alta impedância quanto em transformador de grande porte

---

## Especificação Recomendada

### Para Drives de Velocidade Ajustável (ASD) de 30 HP ou Maiores

Cada ASD deve ser fornecido com filtro harmônico passivo para atender todos os requisitos da IEEE Std 519 (edições 1992 e 2014) para distorção harmônica de tensão e corrente individual e total.

**PCC**: Terminais de entrada do equipamento de mitigação harmônica.

#### Requisitos Técnicos

| Parâmetro | Especificação Padrão | Aplicações Críticas |
|-----------|---------------------|---------------------|
| iTDD | < 8% | < 5% |
| Distorção de tensão de fundo | até 5% | até 2% |
| Desequilíbrio de tensão | até 3% | até 2% |
| Fator de potência | > 0,95 (25% a 100% de carga) | > 0,95 |
| Potência reativa capacitiva | < 15% da potência nominal (≥100HP) | < 15% |
| | < 20% da potência nominal (≤75HP) | < 20% |

#### Requisitos Adicionais
- Mitigação por rede passiva indutor/capacitor (sem componentes eletrônicos ativos)
- Capacidade de operar em ambientes com distorção de tensão até 8% sem derating
- Testes de desempenho em fábrica sob cargas reais de ASD

---

## Estudo de Caso: Sistema HVAC Hospitalar

### Descrição do Sistema

Hospital moderno na área de Boston com backup completo por gerador.

#### Alimentação Elétrica

**Fonte Concessionária:**
- 2 × 2500 kVA, 13,8 kV para 480 V, Z = 5,75%
- Nível de falta: 13,1 kA @ 13,8 kV

**Fonte Gerador:**
- 2 × 2000 kW, 480 V, Xd" = 13%, FP = 0,8

#### Cargas Não Lineares (HVAC)

| Equipamento | Potência | Observação |
|-------------|----------|------------|
| Chillers | 4 × 400 HP | Operação máxima 75% (redundância) |
| AHU com ventiladores EC | 700 HP total | - |
| Ventiladores torre de resfriamento | 4 × 15 HP | - |
| Bombas de água gelada (≥30HP) | 250 HP total | - |
| Bombas de água gelada (≤25HP) | 150 HP total | - |
| Ventiladores diversos (≤20HP) | 150 HP total | Diversidade 75% |

**Carga Linear:** 146 HP (109 kW) com FP = 0,9

### Resultados da Simulação

#### Cenário 1: Apenas Reatores (Sem Mitigação)

**Fonte Concessionária:**
- Limites de corrente: **EXCEDIDOS** no PCC
- Limites de tensão: Atendidos para versão 2014, excedidos para 1992

**Fonte Gerador:**
- Limites de corrente: **EXCEDIDOS**
- Limites de tensão: **EXCEDIDOS** (distorção muito maior devido à maior impedância)

#### Cenário 2: Com Filtros Lineator AUHF (≥30HP)

**Fonte Concessionária:**
- Limites de corrente: ✓ ATENDIDOS
- Limites de tensão: ✓ ATENDIDOS

**Fonte Gerador:**
- Limites de corrente: ✓ ATENDIDOS
- Limites de tensão: ✓ ATENDIDOS

### Conclusão do Estudo de Caso

Ao aplicar filtros harmônicos passivos na entrada de todos os ASDs de 30 HP ou maiores, os requisitos da IEEE Std 519 foram atendidos tanto sob alimentação da concessionária quanto do gerador.

**Não foi necessária** mitigação adicional para os ASDs menores (≤25 HP).

---

## Resumo e Conclusão

A IEEE Std 519 tornou-se a norma aceita para Limites de Harmônicos em Sistemas de Energia na América do Norte e em muitas outras áreas do mundo.

### Desafios Principais
1. Determinar a corrente de demanda máxima na fase de projeto
2. Acumular informações de distribuição e carga para simulação adequada
3. Ter programa de simulação com modelos precisos

### Solução Recomendada

Aplicar os limites harmônicos da norma nos **terminais do equipamento não linear**, combinado com:
- Entendimento de que a corrente máxima de operação pode ser uma boa medida da demanda máxima
- Limites baseados em **iTDD** (não iTHD)

### Benefícios
- Atende os interesses de todas as partes: Usuário Final, Contratante, Concessionária, Fabricante e Projetista
- Simplifica a especificação e verificação
- Garante conformidade mesmo em sistemas complexos

---

## Sobre as Empresas

### Mirus International Inc.
Desde 1991, fornecedora de produtos especializados de qualidade de energia para reduzir ou eliminar problemas harmônicos e economizar energia em sistemas de distribuição elétrica mundialmente.

**Mercados atendidos:**
- Óleo & Gás
- Água/Esgoto
- Chillers e equipamentos HVAC
- Embarcações marítimas
- Data Centers
- Telecomunicações e Radiodifusão

### STULZ USA
Fabricante registrado ISO 9001 de equipamentos de controle ambiental, responsável pelo desenvolvimento de produtos, fabricação e distribuição para o braço norte-americano do grupo internacional STULZ.

**Especialidades:**
- Resfriamento de precisão
- Umidificação ultrassônica
- Desumidificação dessecante
- Soluções para aplicações de missão crítica
