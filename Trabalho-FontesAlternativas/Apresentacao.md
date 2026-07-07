# Roteiro da Apresentação (20-25 minutos)

## Slide 1 — Capa (30s)
- Título: Análise Comparativa PVsyst vs SAM — Estudo de Caso em Brasília-DF
- Integrantes, disciplina, professor, data

## Slide 2 — Agenda (30s)
1. Introdução
2. Artigo de referência
3. Softwares e bancos de dados
4. Novo estudo de caso (UnB)
5. Metodologia
6. Resultados
7. Comparação com artigo original
8. Conclusão

## Slide 3 — Introdução (2 min)
- Crescimento solar no Brasil
- Importância dos softwares de simulação
- SAM como alternativa gratuita

## Slide 4 — Artigo de Referência (2 min)
- UNICAMP, 336,96 kWp, Campinas-SP
- 3 simulações (PVsyst+Met, SAM+Met, SAM+NSRDB)
- Resultados: SAM-NSRDB mais otimista, SAM-Met mais conservador, PVsyst intermediário
- Erros: +6,36%, +11,18%, -1,21%

## Slide 5 — Softwares (2 min)
- PVsyst: pago, referência de mercado, Meteonorm
- SAM: gratuito, NREL, NSRDB, integração Python
- Tabela comparativa de recursos

## Slide 6 — Bancos de Dados (1 min)
- Meteonorm: 8000+ estações, interpolação, cobertura global
- NSRDB: satélite, 4 km, 30 min, cobertura até 20°S no Brasil

## Slide 7 — Novo Estudo de Caso: UnB Brasília (2 min)
- Campus Gama, edifício UED
- 50,4 kWp (subsistema Inversor CSI-50KTL-GI)
- Módulos: CS3W-420P (420 Wp)
- Inclinação 15°, Norte
- Dados reais: 12 meses (artigo Velasco et al., 2024)
- Por que Brasília: NSRDB disponível, clima diferente, latitude menor

## Slide 8 — Metodologia (2 min)
- 3 simulações: PVsyst+Met, SAM+Met, SAM+NSRDB
- Figuras de mérito: Yf, Pr, ED
- Erro percentual: (Real - Simulado) / Real × 100%
- Limites: ±30% mensal, ±10% anual

## Slide 9 — Resultados: Figuras de Mérito (2 min)
- Tabela: Real vs 3 simulações (Yf, Pr, ED)
- Identificar mais otimista e mais conservador

## Slide 10 — Resultados: Geração Mensal (2 min)
- Gráfico de barras (4 séries: Real, PVsyst, SAM-Met, SAM-NSRDB)
- 12 meses no eixo X

## Slide 11 — Resultados: Erro Percentual (2 min)
- Gráfico de linhas (erro mensal das 3 simulações)
- Linhas de referência: ±30%
- Destaque do erro anual vs limite ±10%

## Slide 12 — Comparação com Artigo Original (3 min) ⭐
- Tabela lado a lado: UNICAMP vs UnB
- Os softwares se comportam igual?
- O NSRDB é mais preciso em Brasília (mais perto do equador)?
- Influência do clima/latitude

## Slide 13 — Conclusão (2 min)
- Qual software melhor para Brasília?
- Conclusões mantidas ou diferentes do artigo original?
- Limitações
- Sugestões futuras

## Slide 14 — Referências (30s)

## Slide 15 — Perguntas

---

## Possíveis Perguntas do Professor

1. "Por que usaram apenas o subsistema de 50 kW e não o sistema todo?"
   → Inversor de 75 kW teve falhas operacionais (set-jan), dados comprometidos

2. "Qual a limitação de usar dados de outro artigo?"
   → Não controlamos as condições de medição; porém dados são publicados e revisados por pares

3. "Por que Brasília?"
   → Dentro da cobertura NSRDB, clima diferente, latitude menor

4. "Como garantiram configurações iguais nos dois softwares?"
   → Mesmos módulos, inversores, perdas, orientação; única diferença é o software e/ou base meteorológica

5. "O NSRDB é confiável para o Brasil?"
   → Discutir cobertura, resolução, diferenças vs Meteonorm
