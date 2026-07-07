# Guia de Simulação — SAM (Simulações 2 e 3)

## Objetivo
Realizar DUAS simulações no SAM para o sistema de 99 kWp da UFRJ:
- **Simulação 2:** SAM + Meteonorm (mesmo dado meteorológico do PVsyst)
- **Simulação 3:** SAM + NSRDB (dado nativo do SAM)

---

## Passo 1: Criar Projeto

1. Abrir SAM → **File > New Project**
2. Selecionar: **Photovoltaics > Detailed Photovoltaic Model**
3. Modelo financeiro: **No Financial Model**
4. Clicar **Create**

---

## Passo 2: Dados Meteorológicos

### SIMULAÇÃO 2 — Com Meteonorm
1. Aba **Location and Resource**
2. Clicar em **Browse**
3. Selecionar o arquivo CSV exportado do PVsyst ("Meteonorm_RJ_SAM.csv")
4. Confirmar que os dados carregaram

### SIMULAÇÃO 3 — Com NSRDB
1. Aba **Location and Resource**
2. Clicar em **Download**
3. Coordenadas: Lat **-22.86**, Lon **-43.23**
4. Tipo: **TMY** (Typical Meteorological Year)
5. Se pedir API Key: https://developer.nrel.gov/signup/
6. Clicar Download

**⚠️ NOTA:** Se o NSRDB não retornar dados para essa latitude (limite ~20°S no PSMv3), tente:
- Ajustar latitude para -22.0 ou -21.5
- Ou usar versão GOES (cobertura até 60°S)
- Se não funcionar de jeito nenhum, faça apenas 2 simulações e discuta a limitação no artigo

**A ÚNICA diferença entre Simulação 2 e 3 é o arquivo meteorológico.**

---

## Passo 3: Módulo Fotovoltaico

1. Aba **Module**
2. Modelo: **CEC Performance Model with Module Database**
3. Buscar: Kyocera > KD250GH-4FB2

Se não encontrar, inserir manualmente:

| Parâmetro | Valor |
|-----------|-------|
| Pmax | 250 W |
| Vmpp | 29,8 V |
| Impp | 8,39 A |
| Voc | 36,9 V |
| Isc | 9,09 A |
| Coef. temp. Pmax | -0,46%/°C |
| Coef. temp. Voc | -0,36%/°C |
| Tecnologia | Policristalino |
| Células | 60 |

---

## Passo 4: Inversor

1. Aba **Inverter**
2. Buscar: Kaco > Powador 20TL3

| Parâmetro | Valor |
|-----------|-------|
| Potência nominal CA | 17 kW |
| Faixa MPPT | 460–800 V |
| Eficiência máxima | 98% |
| **Quantidade** | **6** |

Se não encontrar, usar inversor trifásico ~17 kW com faixa MPPT similar.

---

## Passo 5: System Design

| Parâmetro | Valor |
|-----------|-------|
| Modules per string | **18** |
| Strings in parallel | **22** (total) |
| Total modules | **396** (99 kWp) |
| Number of inverters | **6** |
| DC:AC Ratio | 99/102 = ~0,97 |
| Tilt (inclinação) | **10°** |
| Azimuth | **-46°** (ou 314° se SAM usar 0=Norte, sentido horário) |
| Tracking | Fixed |

**⚠️ AZIMUTE NO SAM:**
- Se o SAM usa convenção 0°=Norte, sentido horário: 360° - 46° = **314°**
- Se usa 0°=Norte, Oeste negativo: **-46°**
- Verificar na documentação da versão instalada

---

## Passo 6: Perdas

Usar os **MESMOS valores** do PVsyst:

| Tipo de Perda | Valor |
|---------------|-------|
| Soiling | 2% |
| DC wiring | 1,5% |
| AC wiring | 0,5% |
| Module mismatch | 1,5% |
| Degradation | 1% |
| Availability | 100% |

---

## Passo 7: Simular

1. Clicar **Simulate**
2. Verificar ausência de erros
3. **Repetir para ambas as simulações** (trocar apenas arquivo meteorológico)

---

## Passo 8: Extrair Resultados

1. **Results > Data Tables > Monthly**
2. Coletar: energia mensal em kWh ("Electricity to grid" ou "Annual Energy")
3. Anotar total anual

### Calcular figuras de mérito:
```
Yf = Energia anual (kWh) / 99 (kWp)
Pr = Yf / Yr     onde Yr = Irradiação no plano (kWh/m²) / 1 (kW/m²)
ED = Energia anual total (kWh)
```

---

## Passo 9: Resultados a Preencher

### Simulação 2 — SAM + Meteonorm

| Mês | SAM-Meteonorm (kWh) |
|-----|---------------------|
| Jan | ___ |
| Fev | ___ |
| Mar | ___ |
| Abr | ___ |
| Mai | ___ |
| Jun | ___ |
| Jul | ___ |
| Ago | ___ |
| Set | ___ |
| Out | ___ |
| Nov | ___ |
| Dez | ___ |
| **Total** | **___** |

### Simulação 3 — SAM + NSRDB

| Mês | SAM-NSRDB (kWh) |
|-----|-----------------|
| Jan | ___ |
| Fev | ___ |
| Mar | ___ |
| Abr | ___ |
| Mai | ___ |
| Jun | ___ |
| Jul | ___ |
| Ago | ___ |
| Set | ___ |
| Out | ___ |
| Nov | ___ |
| Dez | ___ |
| **Total** | **___** |

---

## Checklist

### Simulação 2 (SAM + Meteonorm)
- [ ] Arquivo Meteonorm importado do PVsyst
- [ ] Módulo: Kyocera KD250GH-4FB2 (250 Wp)
- [ ] Inversor: Kaco Powador 20TL3 (17 kW) × 6
- [ ] 396 módulos, 18 em série, 22 strings
- [ ] Inclinação 10° / Azimute -46° (NNO)
- [ ] Perdas idênticas ao PVsyst
- [ ] Simulado sem erros
- [ ] Resultados mensais anotados

### Simulação 3 (SAM + NSRDB)
- [ ] NSRDB baixado para lat -22.86, lon -43.23
- [ ] Todos os demais parâmetros IDÊNTICOS à Simulação 2
- [ ] Simulado sem erros
- [ ] Resultados mensais anotados
