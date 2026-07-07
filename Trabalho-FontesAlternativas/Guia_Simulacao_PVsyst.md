# Guia de Simulação — PVsyst (Simulação 1)

## Objetivo
Simular o subsistema FV de 50,4 kWp da UnB (Campus Gama, Brasília-DF) e obter a geração mensal estimada para comparar com os dados reais.

---

## Passo 1: Criar Projeto

1. Abrir PVsyst → **File > New Project > Grid-Connected**
2. Nome: "UnB_Brasilia_50kWp"

---

## Passo 2: Localização e Dados Meteorológicos

1. Em **Site/Meteo**:
   - Latitude: **-15.86**
   - Longitude: **-48.05**
   - Altitude: **1100 m**
   - Fuso horário: **-3 (Brasília)**
2. O PVsyst carregará automaticamente os dados do **Meteonorm**
3. **ANOTAR** os valores mensais de irradiação que o Meteonorm fornecer (GHI, DNI, DHI)

---

## Passo 3: Orientação

| Parâmetro | Valor |
|-----------|-------|
| Tipo | Fixed tilted plane |
| Inclinação (Tilt) | **15°** |
| Azimute | **0°** (Norte — convenção PVsyst hemisfério sul) |

---

## Passo 4: Módulo Fotovoltaico

Buscar no banco de dados:
- **Fabricante:** Canadian Solar
- **Modelo:** CS3W-420P (HiKu)

Se não encontrar o modelo exato, inserir manualmente:

| Parâmetro | Valor |
|-----------|-------|
| Pmax (STC) | 420 W |
| Vmpp | 39,5 V |
| Impp | 10,64 A |
| Voc | 48 V |
| Isc | 11,26 A |
| Eficiência | 19,01% |
| Coef. temperatura Pmax (γ) | -0,37%/°C |
| NOCT | 42°C |
| Tecnologia | Monocristalino PERC |
| Células | Half-cut |

---

## Passo 5: Inversor

Buscar no banco de dados:
- **Fabricante:** Canadian Solar
- **Modelo:** CSI-50KTL-GI

Parâmetros para busca/validação:

| Parâmetro | Valor |
|-----------|-------|
| Potência FV máxima de entrada | 58 kW |
| Tensão máxima de entrada CC | 1100 Vdc |
| Tensão de partida CC | 200 Vdc |
| Faixa de tensão MPPT | **439–850 Vdc** |
| Corrente máxima por MPPT (Imp) | 28,5 A |
| Corrente máxima curto-circuito por MPPT (Isc) | 44,5 A |
| Potência nominal de saída CA | 50 kW |
| Tensão de saída nominal | 380/400 VCA |
| Corrente nominal de saída | 76/72,2 A |
| Eficiência máxima | 98,8% |
| Entradas MPPT | 4 independentes |
| Quantidade | **1** |

Se não encontrar o modelo exato, usar inversor equivalente ~50 kW com faixa MPPT similar.

---

## Passo 6: Configuração do Array

| Parâmetro | Valor |
|-----------|-------|
| Número total de módulos | **118** |
| Potência instalada | **~49,56 kWp** (118 × 420W) |

### Configuração de Strings (conforme artigo da UnB — Inversor 2):
- Entrada MPPT 1: 2 strings em paralelo × 14 módulos em série = 28 módulos
- Entrada MPPT 2: 2 strings em paralelo × 12 módulos em série = 24 módulos
- Entrada MPPT 3: 3 strings em paralelo × 14 módulos em série = 42 módulos
- Entrada MPPT 4: 2 strings em paralelo × 12 módulos em série = 24 módulos
- **Total: 118 módulos**

**Verificações de compatibilidade:**
- Tensão string (14 módulos): 14 × 39,5V = 553V → Faixa MPPT 439–850V ✅
- Tensão string (12 módulos): 12 × 39,5V = 474V → Faixa MPPT 439–850V ✅
- Corrente MPPT (2 strings): 2 × 10,64A = 21,28A → Limite 28,5A ✅
- Corrente MPPT 3 (3 strings): 3 × 10,64A = 31,92A → ⚠️ Acima de 28,5A

> **Nota:** Se o PVsyst indicar erro na entrada MPPT 3, reduza para 2 strings nessa entrada (ajustando o total de módulos). Na prática o sistema real opera assim, então pode aceitar o aviso.

---

## Passo 7: Perdas

| Tipo de Perda | Valor |
|---------------|-------|
| Soiling (sujeira) | 3% (estação seca em Brasília é significativa) |
| Mismatch | 1,5% |
| Perdas ôhmicas CC | 1,5% |
| Perdas ôhmicas CA | 0,5% |
| Degradação | 0% (sistema com <1 ano no período analisado) |
| Indisponibilidade | 0% |
| Sombreamento | Não configurar (telhado sem obstruções) |

**IMPORTANTE:** Anotar EXATAMENTE os valores de perdas usados, para replicar no SAM.

---

## Passo 8: Simular

1. Clicar em **Simulation > Run**
2. Verificar que não há erros/warnings críticos

---

## Passo 9: Extrair Resultados

Coletar do relatório:
1. **Energia mensal injetada na rede (kWh)** — para cada mês
2. **Energia anual total (kWh)**
3. **Performance Ratio (%)** — anual
4. **Yf — Produtividade Final (kWh/kWp)**
5. **Diagrama de perdas** (guardar imagem para o artigo)

---

## Passo 10: Exportar Dados Meteorológicos para o SAM

1. Ir em **Databases > Meteo tables and graphs**
2. Selecionar o site de Brasília
3. **Export > Hourly file > formato SAM CSV**
4. Salvar arquivo (ex: "Meteonorm_Brasilia_SAM.csv")
5. Este arquivo será usado na Simulação 2 (SAM + Meteonorm)

---

## Checklist

- [ ] Localização: -15.86, -48.05, 1100m
- [ ] Base meteorológica: Meteonorm
- [ ] Módulo: CS3W-420P (420 Wp)
- [ ] Inversor: CSI-50KTL-GI (50 kW) — 1 unidade
- [ ] ~120 módulos = 50,4 kWp
- [ ] Inclinação 15° / Azimute Norte
- [ ] Perdas configuradas (anotar valores exatos)
- [ ] Simulação executada sem erros
- [ ] Resultados mensais anotados (kWh por mês)
- [ ] Dados Meteonorm exportados em formato SAM CSV
