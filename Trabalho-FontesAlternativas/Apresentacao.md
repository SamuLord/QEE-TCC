# Roteiro da Apresentação (20-25 minutos)

## Slide 1 — Capa (30s)
- Título: Análise Comparativa PVsyst vs SAM — Estudo de Caso: Estacionamento Solar UFRJ
- Integrantes, disciplina, professor, data

## Slide 2 — Agenda (30s)
1. Introdução
2. Artigo de referência
3. Softwares e bancos de dados
4. Novo estudo de caso (UFRJ)
5. Metodologia
6. Resultados
7. Comparação com artigo original
8. Conclusão

## Slide 3 — Introdução (2 min)
- Brasil: 50 GW solar em 2024 (6º do mundo)
- Importância dos softwares de simulação para viabilidade de projetos
- PVsyst (referência, pago) vs SAM (gratuito, NREL)
- Pergunta: os softwares dão resultados confiáveis? Qual é melhor?

## Slide 4 — Artigo de Referência (2 min)
**Silva et al. (2022) — IX CBENS**
- GMU-UNICAMP, Campinas-SP, 336,96 kWp
- 3 simulações: PVsyst+Meteonorm, SAM+Meteonorm, SAM+NSRDB
- Comparação com 12 meses de dados reais
- Resultados:
  - SAM-NSRDB: mais otimista (erro -1,21%)
  - SAM-Meteonorm: mais conservador (erro +11,18%)
  - PVsyst: intermediário (erro +6,36%)

## Slide 5 — Softwares (2 min)
**PVsyst:**
- Referência de mercado, pago (trial 30 dias)
- Modelagem 3D, diagrama de perdas
- Banco de dados: Meteonorm

**SAM (System Advisor Model):**
- Gratuito, open-source (NREL)
- Banco de dados: NSRDB
- Integração Python, simulação BESS

## Slide 6 — Bancos de Dados Meteorológicos (1 min)
- Meteonorm: 8000+ estações, interpolação, global
- NSRDB: satélite GOES, 4 km, 30 min, Américas (até ~20-60°S)
- Diferença: origem dos dados (estações vs satélite) → afeta resultado

## Slide 7 — Novo Estudo de Caso: UFRJ (2 min)
**Estacionamento Solar — CT/UFRJ, Rio de Janeiro**
- 99 kWp (396 módulos Kyocera KD250GH-4FB2)
- 6 inversores Kaco Powador 20TL3 (17 kW cada)
- Carport — inclinação 10°, azimute 46° Oeste
- Monitorado de 2016 a 2019 (dados públicos)
- [FOTO do estacionamento solar]

**Por que a UFRJ?**
- Potência próxima da UNICAMP (99 vs 337 kWp)
- Latitude quase idêntica (22,86° vs 22,82°) → comparação direta
- Clima diferente: tropical marítimo vs subtropical
- Dados públicos no Zenodo (DOI: 10.5281/zenodo.13334703)

## Slide 8 — Metodologia (2 min)
- 3 simulações com mesmos parâmetros (só muda software/base meteorológica)
- Dados reais: ano 2017 (ECA medida por ION8650A, resolução 15 min)
- Figuras de mérito: Yf, PR, ED
- Erro: (Real - Simulado) / Real × 100%
- Limites: ±30% mensal, ±10% anual

## Slide 9 — Dados Reais 2017 (1 min)
| Mês | Geração (kWh) |
|---|---|
| Jan | 14.989 |
| Fev | 13.863 |
| Mar* | 12.140 |
| ... | ... |
| **Total** | **~138.195** |

- Yf = 1.396 kWh/kWp/ano
- PR médio = 79,5%
- *Mar: dados de 2016

## Slide 10 — Resultados: Figuras de Mérito (2 min)
[Tabela: Real vs 3 simulações — Yf, PR, ED]
- Identificar mais otimista e mais conservador

## Slide 11 — Resultados: Geração Mensal (2 min)
[Gráfico de barras — 4 séries: Real, PVsyst, SAM-Met, SAM-NSRDB]
- 12 meses no eixo X

## Slide 12 — Resultados: Erro Percentual (2 min)
[Gráfico de linhas — erro mensal]
- Linhas de referência: ±30%
- Destaque erro anual vs ±10%

## Slide 13 — Comparação com Artigo Original (3 min) ⭐
| Aspecto | UNICAMP | UFRJ |
|---|---|---|
| Latitude | 22,82°S | 22,86°S |
| Clima | Subtropical (Cwa) | Tropical marítimo (Af) |
| Potência | 337 kWp | 99 kWp |
| Mais otimista | SAM-NSRDB | ___ |
| Mais conservador | SAM-Met | ___ |

**Discussão:**
- Mesmas conclusões?
- Azimute 46° Oeste afeta resultado?
- Clima mais úmido/nublado influencia?

## Slide 14 — Conclusão (2 min)
- Qual software melhor para o Rio de Janeiro?
- Conclusões confirmam ou contradizem Campinas?
- Limitações (azimute, março/2016, degradação)
- Sugestões futuras

## Slide 15 — Referências (30s)

## Slide 16 — Perguntas

---

## Possíveis Perguntas do Professor

1. "Por que o azimute é 46° Oeste e não Norte?"
   → Decisão arquitetônica do carport. A inclinação ideal para RJ seria ~22° Norte, mas foi reduzida para 10° e rotacionada para NNO por questões de design.

2. "O NSRDB funciona para o Rio de Janeiro?"
   → No limite da cobertura (22,86°S). O artigo da UNICAMP (22,82°S) conseguiu usar. Se não funcionar, discutimos a limitação.

3. "Por que falta Março de 2017?"
   → Falha no sistema de monitoramento naquele mês. Complementamos com dados de Março/2016 do mesmo sistema.

4. "A diferença de potência (99 vs 337 kWp) invalida a comparação?"
   → Não, pois usamos figuras de mérito normalizadas (Yf em kWh/kWp, PR adimensional).

5. "Qual a influência do azimute não-ideal na simulação?"
   → Os softwares consideram a orientação real. Se a simulação capturar corretamente o azimute de 46°W, o resultado deve refletir a perda por orientação.
