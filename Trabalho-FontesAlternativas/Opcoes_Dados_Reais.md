# Opções de Dados Reais de Geração FV — Links para Verificar

## RESUMO: O que você precisa encontrar em cada link

Procure por:
- Tabela com **geração mensal em kWh ou MWh** (12 meses ou mais)
- Informações do sistema: **modelo dos módulos, inversor, potência (kWp), inclinação, localização**
- De preferência potência > 50 kWp (mais similar ao artigo original de 337 kWp)
- Localização que tenha cobertura do **NSRDB** (Américas: -60°S a +60°N, 175°W a 25°W)

---

## OPÇÃO 1: PVDAQ — NREL (EUA) ⭐ DADOS JÁ CONFIRMADOS

Já consegui acessar esses dados. O sistema mais promissor é:

**Sistema 34: Andre Agassi Preparatory Academy, Las Vegas, NV**
- Potência: **146,64 kW**
- Módulos: Sharp nu-u240f1 (mono-Si), 611 unidades
- Inversor: Satcon 135 kW (1 unidade central)
- Inclinação: 11,2° / Azimute: 180° (Sul — hemisfério norte)
- Lat: 36,19°N / Lon: -115,16°W (Las Vegas)
- Dados: a partir de outubro/2010, resolução 15 min
- NSRDB: ✅ (EUA)
- Coluna útil: `ac_power_hw` (potência CA em W, a cada 15 min)

Para usar: preciso somar os dados de 15 min para obter energia mensal em kWh.
**Posso fazer isso se você confirmar que quer este sistema.**

---

## OPÇÃO 2: Kaggle — Solar Power Generation Data (Índia)

**Link:** https://www.kaggle.com/datasets/anikannal/solar-power-generation-data

- Duas usinas solares na Índia (~34 dias de dados)
- Dados de potência DC e AC por inversor
- Inclui dados de irradiação e temperatura
- **Problema:** Apenas ~34 dias (não 12 meses)
- **NSRDB:** ❌ (Índia fora da cobertura NSRDB)
- **Veredicto:** Não serve para 12 meses, mas bom para teste rápido

---

## OPÇÃO 3: GitHub — Solar Power Datasets and Resources

**Link:** https://github.com/Charlie5DH/Solar-Power-Datasets-and-Resources

Lista compilada com links para vários datasets solares. Inclui:
- PVDAQ (NREL)
- DKA Solar Centre (Austrália)
- Kaggle datasets
- OEDI datasets
- Outros

**Vale verificar manualmente** — pode ter algum dataset que não encontrei.

---

## OPÇÃO 4: UnB — Brasília (dados que já temos) ⭐

**Link:** https://www.mdpi.com/2071-1050/16/24/11212

- Já extraímos os dados
- 50,4 kWp, 12 meses
- Canadian Solar CS3W-420P
- Brasília-DF (15,86°S)
- NSRDB: ✅

---

## OPÇÃO 5: DKA Solar Centre — Austrália (dados em tempo real)

**Link:** http://www.dkasolarcentre.com.au/

- ~25 sistemas diferentes em Alice Springs
- Dados de geração disponíveis online
- **NSRDB:** ❌ (Austrália) — só dá para fazer 2 simulações (sem SAM+NSRDB)
- Verifique se tem download CSV no site

---

## OPÇÃO 6: Nature Scientific Data — High-resolution PV dataset (3 anos)

**Link:** https://www.nature.com/articles/s41597-025-04397-y

- Dataset open-source de geração FV em ambiente urbano
- 3 anos de dados em alta resolução
- Verificar localização e se inclui dados mensais

---

## OPÇÃO 7: Artigo Nordeste Brasil — Usina FV + dados anuais

**Link:** https://pubs.aip.org/aip/jrse/article/15/2/023501/2879452

"A comparative study to determine the photovoltaic annual energy generation in the Brazilian Northeast"
- Compara métodos de estimativa com geração real de 1 ano
- Usina no Nordeste brasileiro
- Verificar se os dados mensais estão nas tabelas do artigo
- NSRDB: ✅ (Nordeste < 20°S)

---

## OPÇÃO 8: MDPI — Utility-Scale PV Performance Ratio Evolution (Brasil subtropical)

**Link:** https://www.mdpi.com/2076-3417/12/21/11306

"Study of the Evolution of the Performance Ratio of Photovoltaic Plants Operating in a Utility-Scale Installation Located at a Subtropical Climate Zone Using Mixed-Effects Linear Modeling"
- Usinas utility-scale no Brasil (zona subtropical)
- Pode ter dados de geração mensal
- Verificar se é open access e se tem tabelas com kWh

---

## OPÇÃO 9: PVDAQ — Outros sistemas maiores encontrados

| ID | Nome | Potência | Local |
|----|------|----------|-------|
| 34 | Andre Agassi Academy - Building A | **146,64 kW** | Las Vegas, NV |
| 35 | Andre Agassi Academy - Gymnasium | **121,68 kW** | Las Vegas, NV |
| 1199 | Distributed Sun - Hunt Valley | **52,92 kW** | Maryland |
| 1200 | Distributed Sun - BWI Hilton | **51,84 kW** | Maryland |

Se quiser um dos PVDAQ, confirme o número do sistema que eu baixo e processo os dados mensais.

---

## OPÇÃO 10: EIA — US Energy Information Administration

**Link:** https://www.eia.gov/electricity/monthly/

Dados mensais de geração solar por estado dos EUA (agregado, não por planta individual).
Não ideal para comparação planta-a-planta, mas pode servir como referência regional.

---

## MINHA RECOMENDAÇÃO DE PRIORIDADE

1. **PVDAQ Sistema 34** (146 kW, Las Vegas) — já tenho acesso, posso processar
2. **UnB Brasília** (50 kWp) — já temos os dados prontos
3. **Artigo Nordeste** (link 7) — verificar se tem dados mensais
4. **MDPI Utility-Scale** (link 8) — verificar se tem dados de geração

---

## O QUE VERIFICAR EM CADA LINK

Ao abrir cada artigo/site, procure:
1. Uma **tabela com valores de energia (kWh ou MWh) por mês** durante 12+ meses
2. As **especificações do sistema** (módulos, inversor, inclinação, potência)
3. A **localização exata** (latitude/longitude ou endereço)
4. Se a latitude está **nas Américas** (para ter cobertura NSRDB)
