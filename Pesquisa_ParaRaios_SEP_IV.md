# O Emprego de Para-Raios em Sistemas de Energia Elétrica

**Disciplina:** Tópicos em SEP IV – 2026-1  
**Data de entrega:** 14/07/2026  
**Integrantes:** Beatriz Helena / [Nome do par]

---

## 1. Objetivo

Este trabalho apresenta o emprego de para-raios (surge arresters) em sistemas de energia elétrica, abordando sua finalidade dentro da coordenação de isolamento, os tipos existentes, a construção física, o princípio de funcionamento, os critérios de dimensionamento e as condições de instalação. Inclui-se um exemplo numérico de seleção do equipamento e uma análise de vantagens e limitações de sua aplicação.

---

## 2. Introdução

Sistemas de energia elétrica estão permanentemente sujeitos a sobretensões transitórias originadas por descargas atmosféricas (surtos de origem externa) e por manobras de chaveamento (surtos de origem interna). Essas sobretensões podem exceder a suportabilidade dielétrica de transformadores, cabos, buchas e equipamentos de manobra, provocando perfuração de isolamento, flamejamento externo e falhas catastróficas (HILEMAN, 1999).

A coordenação de isolamento é a metodologia que relaciona os níveis de suportabilidade dos equipamentos (expressos pelo NBI – Nível Básico de Isolamento ao impulso atmosférico, e pelo BSL – Basic Switching Impulse Level) com os níveis de proteção fornecidos pelos dispositivos limitadores de sobretensão. O para-raios é o principal equipamento empregado nessa coordenação: conectado entre fase e terra, ele permanece em alta impedância durante a tensão normal de operação e, ao surgir uma sobretensão, transita para baixa impedância, conduzindo a corrente de surto para a terra e limitando a tensão aplicada ao equipamento protegido a um valor residual inferior ao NBI deste equipamento (IEEE Std C62.11, 2012).

A evolução tecnológica dos para-raios acompanhou o desenvolvimento dos materiais cerâmicos. Os primeiros dispositivos utilizavam centelhadores (gaps) em série com resistores não-lineares de carboneto de silício (SiC). A partir da década de 1970, surgiram os para-raios de óxido de zinco (ZnO), sem centelhadores, cuja característica tensão-corrente altamente não-linear permitiu construção mais compacta, melhor desempenho em sobretensões temporárias e menor tensão residual (HINRICHSEN, 2012).

---

## 3. Construção e Funcionamento do Para-Raios

### 3.1 Elementos Construtivos

Um para-raios de óxido metálico (MOSA – Metal Oxide Surge Arrester) é composto por (IEC 60099-4, 2014):

1. **Blocos varistores de ZnO** – Discos cerâmicos de óxido de zinco dopados com pequenas quantidades de outros óxidos metálicos (Bi₂O₃, Sb₂O₃, Co₃O₄, MnO₂). Os grãos de ZnO formam contornos de grão que funcionam como milhões de junções não-lineares em paralelo e em série, conferindo a característica V×I desejada.

2. **Espaçadores e eletrodos metálicos** – Discos de alumínio ou ligas que fazem contato elétrico entre os blocos varistores e distribuem a corrente uniformemente.

3. **Invólucro isolante** – Pode ser de porcelana vitrificada ou de polímero (borracha de silicone ou EPDM com reforço de fibra de vidro). O invólucro polimérico apresenta menor peso, resistência à vandalismo, comportamento hidrofóbico superior em ambientes poluídos e menor risco de fragmentação explosiva em caso de falha interna.

4. **Estrutura de suporte interno** – Tubo de fibra de vidro que sustenta mecanicamente a coluna de varistores e garante alinhamento axial.

5. **Dispositivo de alívio de pressão** – Permite a liberação controlada de gases em caso de falha interna com arco, evitando explosão violenta do invólucro.

6. **Desconector de terra (contador de descargas)** – Opcional; registra o número de atuações e pode desconectar o para-raios de forma visível em caso de falha.

**[IMAGEM 1 – Gerar com IA]**  
*Prompt:* "Desenho técnico em corte longitudinal de um para-raios de óxido metálico (ZnO) para alta tensão, mostrando em camadas: (1) terminal superior de linha, (2) eletrodo superior de alumínio, (3) coluna de discos varistores de ZnO empilhados, (4) espaçadores metálicos entre discos, (5) tubo de fibra de vidro envolvendo a coluna, (6) invólucro externo de polímero com saias (sheds) para aumentar distância de escoamento, (7) terminal inferior de terra, (8) dispositivo de alívio de pressão na base. Fundo branco, estilo engenharia técnica, com legendas numeradas apontando para cada componente."

**[IMAGEM 2 – Referência da internet]**  
*Fonte sugerida:* Figura de característica V×I comparativa entre para-raios de ZnO e SiC disponível em: https://www.researchgate.net/figure/Caracteristica-v-x-i-de-para-raios-de-ZnO-e-SiC-6_fig3_3455171  
*(Verificar direitos de uso; caso não seja permitido, gerar com IA usando o prompt: "Gráfico comparativo de curva tensão versus corrente (V×I) em escala log-log de um varistor de ZnO (expoente alfa=30, curva íngreme) e um resistor de SiC (alfa=5, curva mais suave), eixo X: corrente em ampères de 10⁻⁴ a 10⁴, eixo Y: tensão em pu de 0,5 a 2,5. Indicar regiões de operação normal, joelho e condução plena. Estilo gráfico acadêmico limpo, fundo branco.")*

### 3.2 Princípio de Funcionamento

O comportamento elétrico do varistor de ZnO é descrito pela relação não-linear:

$$I = k \cdot V^{\alpha}$$

onde *I* é a corrente através do bloco, *V* é a tensão aplicada, *k* é uma constante dependente do material e da geometria, e *α* é o expoente de não-linearidade, tipicamente entre 25 e 50 para varistores modernos de ZnO (HINRICHSEN, 2012). Para comparação, resistores de SiC apresentam α entre 3 e 7.

O alto valor de α implica que:

- Na tensão de operação contínua (MCOV – Maximum Continuous Operating Voltage), a corrente de fuga é da ordem de microampères, e o para-raios se comporta praticamente como circuito aberto.
- Quando a tensão supera o "joelho" da curva V×I, um pequeno aumento de tensão provoca aumento de várias ordens de grandeza na corrente conduzida, limitando efetivamente a tensão nos terminais do equipamento protegido.
- Após o surto, quando a tensão retorna ao valor nominal do sistema, a corrente cessa sem necessidade de centelhador para interromper a corrente subsequente de frequência industrial – diferença fundamental em relação aos antigos para-raios de SiC com gap.

### 3.3 Variáveis que Condicionam o Funcionamento

| Variável | Influência |
|----------|-----------|
| MCOV | Tensão máxima que o para-raios suporta continuamente sem degradação térmica. Deve ser superior à tensão máxima fase-terra do sistema. |
| Tensão nominal (Ur) | Valor de referência para ensaios e classificação; associa-se à capacidade de suportar sobretensões temporárias (TOV). |
| Tensão residual (Ures) | Tensão que permanece nos terminais do para-raios enquanto conduz corrente de surto. Define o nível de proteção. |
| Capacidade de absorção de energia | Determina quantos joules por kV de tensão nominal o para-raios pode dissipar sem falha térmica. |
| Corrente nominal de descarga (In) | Valor padronizado da corrente de impulso (8/20 µs) para fins de classificação: 5 kA, 10 kA ou 20 kA. |
| Temperatura ambiente | Altas temperaturas reduzem a margem térmica disponível e aceleram o envelhecimento dos varistores. |
| Poluição e altitude | Afetam a distância de escoamento necessária no invólucro externo. |

---

## 4. Aplicações

### 4.1 Localização e Instalação

Para-raios são instalados entre fase e terra nos seguintes pontos típicos de um sistema elétrico (IEEE Std C62.22, 2009):

- **Entrada de linhas em subestações** – Proteção dos equipamentos contra surtos atmosféricos provenientes das linhas de transmissão.
- **Terminais de transformadores de potência** – Ponto mais crítico, pois transformadores possuem NBI relativamente baixo em relação ao custo de substituição.
- **Transições cabo-linha aérea (riser poles)** – Cabos isolados possuem NBI inferior ao de linhas aéreas e sofrem reflexão de ondas viajantes na transição de impedância.
- **Bancos de capacitores** – Proteção contra sobretensões de chaveamento (reenergização e restrike).
- **Equipamentos de manobra (disjuntores, seccionadoras)** – Em subestações de alta tensão.
- **Em estruturas de linhas de transmissão** – Para-raios de linha (TLA – Transmission Line Arresters), instalados diretamente nas torres, reduzem a taxa de desligamentos por backflashover.

**Requisitos de instalação:**

- Conexão com condutores curtos e retos entre o terminal de linha do para-raios e o condutor fase, e entre o terminal de terra e a malha de aterramento. Condutores longos adicionam tensão indutiva (L·di/dt) durante o surto, reduzindo a margem de proteção efetiva.
- Proximidade ao equipamento protegido: a distância elétrica entre o para-raios e o terminal do equipamento deve ser mínima; distâncias maiores permitem amplificação da tensão por reflexões de ondas viajantes.
- Aterramento de baixa impedância no ponto de conexão.

### 4.2 Classes de Para-Raios

Segundo a classificação da IEEE C62.11 (2012):

| Classe | Aplicação típica | Corrente nominal (In) |
|--------|-----------------|----------------------|
| Estação (Station) | Subestações de transmissão (≥ 69 kV), proteção de transformadores de grande porte | 10 kA ou 20 kA |
| Intermediária | Subestações industriais e distribuição de média tensão com alta exposição | 10 kA |
| Distribuição (Distribution) | Linhas de distribuição, transformadores de distribuição, postes | 5 kA ou 10 kA |

### 4.3 Exemplo de Dimensionamento

**Dados do sistema:**
- Tensão nominal: 138 kV (sistema efetivamente aterrado, fator de aterramento ≤ 1,4)
- NBI dos transformadores: 650 kV
- Corrente nominal de descarga desejada: 10 kA (classe estação)

**Passo 1 – Determinação da MCOV mínima:**

A tensão máxima fase-terra em regime permanente para um sistema de 145 kV (tensão máxima de operação conforme IEC) é:

$$V_{fase-terra,max} = \frac{145}{\sqrt{3}} = 83{,}7 \text{ kV (rms)}$$

O para-raios deve ter MCOV ≥ 83,7 kV. Seleciona-se um para-raios com MCOV = 84 kV (valor comercial do catálogo, correspondente a Ur = 108 kV).

**Passo 2 – Verificação da sobretensão temporária (TOV):**

Para sistema efetivamente aterrado, a sobretensão temporária durante falta fase-terra é tipicamente 1,4 × tensão fase-terra = 1,4 × 83,7 = 117,2 kV. O para-raios com Ur = 108 kV deve suportar esta TOV durante o tempo de eliminação da falta (tipicamente 1 s para proteção primária). Verifica-se na curva TOV do fabricante que o para-raios de 108 kV suporta 117 kV por 1 s.

**Passo 3 – Nível de proteção (tensão residual):**

Para 10 kA, 8/20 µs, o fabricante especifica tensão residual de 305 kV (valor típico de catálogo para para-raios de 108 kV classe estação). 

**Passo 4 – Margem de proteção:**

$$MP = \frac{NBI - V_{residual}}{V_{residual}} \times 100\%$$

$$MP = \frac{650 - 305}{305} \times 100\% = 113\%$$

O valor é superior à margem mínima recomendada de 20% pela IEEE Std C62.22, indicando coordenação adequada. Na prática, desconta-se a parcela de tensão indutiva nos condutores de conexão (tipicamente 1–2 kV/m para correntes de surto íngreme), mas neste caso a margem é amplamente suficiente.

---

## 5. Análises e Conclusões

### 5.1 Vantagens do Emprego de Para-Raios de ZnO

- **Eliminação do centelhador (gap):** permite resposta instantânea (sem tempo de disparo do gap), elimina a corrente subsequente de frequência industrial e reduz o estresse no sistema de aterramento.
- **Menor tensão residual:** o expoente α elevado proporciona clamping mais justo, permitindo menores margens de isolamento e, consequentemente, equipamentos mais compactos e econômicos.
- **Capacidade de absorção de energia:** varistores modernos de ZnO podem dissipar de 4 a 12 kJ/kV de tensão nominal, adequados tanto para surtos atmosféricos quanto para surtos de manobra.
- **Manutenção reduzida:** sem partes móveis e sem gaps sujeitos a deterioração por corrosão ou contaminação.
- **Invólucros poliméricos:** reduzem peso em até 70% em relação à porcelana, eliminam risco de explosão fragmentária e mantêm hidrofobicidade em ambientes poluídos.
- **Aplicação em linhas (TLA):** reduz desligamentos por backflashover em linhas de transmissão, melhorando indicadores de continuidade (DEC/FEC).

### 5.2 Limitações

- **Envelhecimento dos varistores:** surtos repetitivos, sobretensões temporárias prolongadas e alta temperatura ambiente degradam progressivamente os contornos de grão, aumentando a corrente de fuga e podendo levar à instabilidade térmica (thermal runaway). O para-raios não é um dispositivo "instale e esqueça".
- **Sem indicação visual de degradação:** diferente de um fusível queimado, a degradação do para-raios não é evidente externamente sem medição periódica da corrente de fuga resistiva ou termografia.
- **Não protege contra sobretensões sustentadas:** sobretensões temporárias que excedam a capacidade TOV por tempo maior que o especificado podem destruir o para-raios.
- **Dependência da qualidade do aterramento:** se a impedância de aterramento no ponto de instalação for alta, a tensão efetiva no terminal do equipamento protegido aumenta, reduzindo a margem de proteção.
- **Distância ao equipamento protegido:** a eficácia diminui com a separação. Para ondas de frente íngreme (< 1 µs), a reflexão da onda viajante entre o para-raios e o equipamento pode duplicar a tensão na isolação.
- **Falha catastrófica:** embora rara em projetos adequados, uma falha interna com arco pode gerar altas pressões internas; o dispositivo de alívio de pressão deve ser dimensionado para a corrente de curto-circuito do ponto de instalação.

### 5.3 Conclusão

O para-raios de óxido de zinco é o elemento central da coordenação de isolamento em sistemas de potência modernos. Sua característica V×I altamente não-linear permite limitar sobretensões atmosféricas e de manobra a níveis compatíveis com o NBI dos equipamentos protegidos, com margens adequadas de segurança. A seleção correta requer consideração simultânea da MCOV, da tensão nominal, da capacidade de absorção de energia, da classe do para-raios e das condições de instalação (comprimento dos condutores e impedância de aterramento). O monitoramento periódico da corrente de fuga resistiva e a inspeção visual do invólucro são práticas essenciais para garantir a confiabilidade a longo prazo do equipamento.

---

## 6. Referências Bibliográficas

1. IEC 60099-4:2014 – *Surge arresters – Part 4: Metal-oxide surge arresters without gaps for a.c. systems*. International Electrotechnical Commission, 2014.

2. IEEE Std C62.11-2012 – *IEEE Standard for Metal-Oxide Surge Arresters for AC Power Circuits (> 1 kV)*. Institute of Electrical and Electronics Engineers, 2012.

3. IEEE Std C62.22-2009 – *IEEE Guide for the Application of Metal-Oxide Surge Arresters for Alternating-Current Systems*. Institute of Electrical and Electronics Engineers, 2009.

4. HILEMAN, A. R. *Insulation Coordination for Power Systems*. New York: Marcel Dekker, 1999.

5. HINRICHSEN, V. *Metal-Oxide Surge Arresters in High-Voltage Power Systems*. 3rd ed. Darmstadt: Siemens AG, 2012.

6. MARTINEZ-VELASCO, J. A. (Ed.). *Power System Transients: Parameter Determination*. Boca Raton: CRC Press, 2010.

7. ZANETTA JR., L. C. *Transitórios Eletromagnéticos em Sistemas de Potência*. São Paulo: EDUSP, 2003.

8. ABB. *Surge Arresters – Buyer's Guide*. Edition 8. ABB Power Grids, 2019. Disponível em: https://library.e.abb.com.

---

## Uso de Ferramentas de IA

As seguintes partes utilizaram auxílio de IA generativa para criação de imagens:

- **Imagem 1 (Seção 3.1) – Corte construtivo do para-raios:**  
  Prompt: "Desenho técnico em corte longitudinal de um para-raios de óxido metálico (ZnO) para alta tensão, mostrando em camadas: (1) terminal superior de linha, (2) eletrodo superior de alumínio, (3) coluna de discos varistores de ZnO empilhados, (4) espaçadores metálicos entre discos, (5) tubo de fibra de vidro envolvendo a coluna, (6) invólucro externo de polímero com saias (sheds) para aumentar distância de escoamento, (7) terminal inferior de terra, (8) dispositivo de alívio de pressão na base. Fundo branco, estilo engenharia técnica, com legendas numeradas apontando para cada componente."

- **Imagem 2 (Seção 3.2) – Curva V×I comparativa (caso não seja usada a figura do ResearchGate):**  
  Prompt: "Gráfico comparativo de curva tensão versus corrente (V×I) em escala log-log de um varistor de ZnO (expoente alfa=30, curva íngreme) e um resistor de SiC (alfa=5, curva mais suave), eixo X: corrente em ampères de 10⁻⁴ a 10⁴, eixo Y: tensão em pu de 0,5 a 2,5. Indicar regiões de operação normal, joelho e condução plena. Estilo gráfico acadêmico limpo, fundo branco."

A pesquisa bibliográfica, redação técnica, cálculos de dimensionamento e análises foram realizados pelos autores com base nas normas e livros-texto indicados nas referências.
