# Guia de Simulação — SAM (Simulação 2 e 3)

## Objetivo
Realizar DUAS simulações no SAM para o mesmo sistema de 50,4 kWp:
- **Simulação 2:** SAM + Meteonorm (mesmo dado meteorológico do PVsyst)
- **Simulação 3:** SAM + NSRDB (dado meteorológico nativo do SAM)

---

## Passo 1: Criar Projeto

1. Abrir SAM → **File > New Project**
2. Selecionar: **Photovoltaics > Detailed Photovoltaic Model**
3. Modelo financeiro: **No Financial Model** (só geração de energia)
4. Clicar **Create**

---

## Passo 2: Dados Meteorológicos

### SIMULAÇÃO 2 — Com Meteonorm
1. Aba **Location and Resource**
2. Clicar em **Browse** (não Download)
3. Selecionar o arquivo CSV exportado do PVsyst ("Meteonorm_Brasilia_SAM.csv")
4. Confirmar que os dados carregaram (GHI, DNI, DHI, temperatura, vento)

### SIMULAÇÃO 3 — Com NSRDB
1. Aba **Location and Resource**
2. Clicar em **Download** (ícone de nuvem)
3. Coordenadas: Lat **-15.86**, Lon **-48.05**
4. Tipo de dado: **TMY** (Typical Meteorological Year)
5. Se pedir API Key: criar conta grátis em https://developer.nrel.gov/signup/
6. Clicar Download e aguardar

**⚠️ A ÚNICA diferença entre Simulação 2 e 3 é o arquivo meteorológico. Todo o resto é IDÊNTICO.**

---

## Passo 3: Módulo Fotovoltaico

1. Aba **Module**
2. Modelo: **CEC Performance Model with Module Database**
3. Buscar: Canadian Solar > CS3W-420P

Se não encontrar, inserir manualmente:

| Parâmetro | Valor |
|-----------|-------|
| Pmax | 420 W |
| Vmpp | 39,5 V |
| Impp | 10,64 A |
| Voc | 48 V |
| Isc | 11,26 A |
| Coef. temp. Pmax | -0,37%/°C |
| NOCT | 42°C |
| Eficiência | 19,01% |

---

## Passo 4: Inversor

1. Aba **Inverter**
2. Buscar: Canadian Solar > CSI-50KTL-GI

Se não encontrar, usar inversor ~50 kW com:
| Parâmetro | Valor |
|-----------|-------|
| Potência CA nominal | ~50 kW |
| Eficiência máxima | >97% |
| Faixa MPPT | 180–1000 Vdc |

**Quantidade de inversores: 1**

---

## Passo 5: System Design

| Parâmetro | Valor |
|-----------|-------|
| Modules per string | 12-14 (verificar tensão MPPT) |
| Strings in parallel | Calcular para totalizar ~120 módulos |
| Number of inverters | 1 |
| Total modules | ~120 (50,4 kWp) |
| DC:AC Ratio | ~1.0 |
| Tilt (inclinação) | **15°** |
| Azimuth | **0°** (Norte — no SAM, 0° = Norte) |
| Tracking | Fixed |
| Ground coverage ratio | 0.4 |

**⚠️ AZIMUTE NO SAM:** Para hemisfério sul, o painel aponta para Norte = **0°** no SAM.

---

## Passo 6: Perdas

Usar os **MESMOS valores** do PVsyst:

| Tipo de Perda | Valor |
|---------------|-------|
| Soiling | 3% |
| DC wiring | 1,5% |
| AC wiring | 0,5% |
| Module mismatch | 1,5% |
| Nameplate derating | 0% |
| Availability | 100% |
| Degradation | 0% |

---

## Passo 7: Simular

1. Clicar **Simulate** (botão verde)
2. Verificar que não há erros no log
3. **Repetir para ambas as simulações** (trocar apenas o arquivo meteorológico)

---

## Passo 8: Extrair Resultados

1. **Results > Data Tables > Monthly**
2. Coletar: energia mensal em kWh (AC energy ou "Electricity to grid")
3. Anotar o total anual

### Calcular figuras de mérito:
```
Yf = Energia anual (kWh) / 50,4 (kWp)
Pr = Yf / Yr     onde Yr = Irradiação no plano (kWh/m²) / 1 (kW/m²)
ED = Energia anual total (kWh)
```

---

## Passo 9: Resultados a Preencher

### Simulação 2 — SAM + Meteonorm

| Mês | SAM-Meteonorm (kWh) |
|-----|---------------------|
| Mar/2022 | ___ |
| Abr/2022 | ___ |
| Mai/2022 | ___ |
| Jun/2022 | ___ |
| Jul/2022 | ___ |
| Ago/2022 | ___ |
| Set/2022 | ___ |
| Out/2022 | ___ |
| Nov/2022 | ___ |
| Dez/2022 | ___ |
| Jan/2023 | ___ |
| Fev/2023 | ___ |
| **Total** | **___** |

### Simulação 3 — SAM + NSRDB

| Mês | SAM-NSRDB (kWh) |
|-----|-----------------|
| Mar/2022 | ___ |
| Abr/2022 | ___ |
| Mai/2022 | ___ |
| Jun/2022 | ___ |
| Jul/2022 | ___ |
| Ago/2022 | ___ |
| Set/2022 | ___ |
| Out/2022 | ___ |
| Nov/2022 | ___ |
| Dez/2022 | ___ |
| Jan/2023 | ___ |
| Fev/2023 | ___ |
| **Total** | **___** |

---

## Checklist

### Simulação 2 (SAM + Meteonorm)
- [ ] Arquivo Meteonorm importado do PVsyst
- [ ] Módulo: CS3W-420P (420 Wp)
- [ ] Inversor: CSI-50KTL-GI (50 kW) × 1
- [ ] ~120 módulos, 50,4 kWp
- [ ] Inclinação 15° / Azimute 0° (Norte)
- [ ] Perdas idênticas ao PVsyst
- [ ] Simulado sem erros
- [ ] Resultados mensais anotados

### Simulação 3 (SAM + NSRDB)
- [ ] NSRDB baixado para lat -15.86, lon -48.05
- [ ] Todos os demais parâmetros IDÊNTICOS à Simulação 2
- [ ] Simulado sem erros
- [ ] Resultados mensais anotados
