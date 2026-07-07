# Guia de Simulação — PVsyst (Simulação 1)

## Objetivo
Simular o sistema FV de 99 kWp do Estacionamento Solar da UFRJ e obter a geração mensal estimada para comparar com os dados reais de 2017.

---

## Passo 1: Criar Projeto

1. Abrir PVsyst → **File > New Project > Grid-Connected**
2. Nome: "UFRJ_Estacionamento_Solar_99kWp"

---

## Passo 2: Localização e Dados Meteorológicos

| Parâmetro | Valor |
|-----------|-------|
| Latitude | **-22.86** |
| Longitude | **-43.23** |
| Altitude | **11 m** |
| Fuso horário | **-3 (Brasília)** |

- O PVsyst carregará automaticamente os dados do **Meteonorm**
- **ANOTAR** os valores mensais de irradiação (GHI, DNI, DHI)

---

## Passo 3: Orientação

| Parâmetro | Valor |
|-----------|-------|
| Tipo | Fixed tilted plane |
| Inclinação (Tilt) | **10°** |
| Azimute | **-46°** (46° para Oeste = Noroeste; no PVsyst hemisfério sul: Oeste é negativo*) |

**⚠️ ATENÇÃO AZIMUTE:** No PVsyst, para hemisfério sul, Norte = 0°, Oeste = -90°, Leste = +90°. O sistema da UFRJ aponta 46° para Oeste do Norte, portanto: **Azimute = -46°** (ou verificar a convenção da sua versão do PVsyst).

Se tiver dúvida, configure Azimute = 0° (Norte) e veja o resultado — depois ajuste para -46° e compare.

---

## Passo 4: Módulo Fotovoltaico

Buscar no banco de dados:
- **Fabricante:** Kyocera
- **Modelo:** KD250GH-4FB2

Se não encontrar o modelo exato, inserir manualmente:

| Parâmetro | Valor |
|-----------|-------|
| Pmax (STC) | 250 W |
| Vmpp | 29,8 V |
| Impp | 8,39 A |
| Voc | 36,9 V |
| Isc | 9,09 A |
| Eficiência | 15,1% |
| Coef. temperatura Pmax | -0,46%/°C |
| Coef. temperatura Voc | -0,36%/°C |
| Tecnologia | Policristalino |
| Células | 60 |

---

## Passo 5: Inversor

Buscar no banco de dados:
- **Fabricante:** Kaco (ou Kaco New Energy)
- **Modelo:** Powador 20TL3

| Parâmetro | Valor |
|-----------|-------|
| Potência nominal CA | 17 kW |
| Tensão máxima CC | 1000 V |
| Faixa MPPT | **460–800 V** |
| Corrente máxima CC | 2 × 18,6 A |
| Eficiência máxima | 98% |
| **Quantidade** | **6 inversores** |

Se não encontrar o modelo exato, usar inversor trifásico ~17 kW com faixa MPPT ~460-800V.

---

## Passo 6: Configuração do Array

| Parâmetro | Valor |
|-----------|-------|
| Número total de módulos | **396** |
| Potência instalada | **99 kWp** (396 × 250W) |
| Arranjos | 22 arranjos de 18 módulos em série |
| Módulos em série por string | **18** |
| Strings em paralelo (total) | **22** |
| Inversores | **6** |

### Distribuição por inversor:
- Cada inversor recebe ~3-4 strings (22 strings / 6 inversores ≈ 3,67)
- String Boxes 01 a 04: 4 strings cada (4×18 = 72 módulos por SB)
- String Box 05: 4 strings (72 módulos)
- String Box 06: 2 strings (36 módulos)

### Verificação de compatibilidade:
- Tensão string: 18 × 29,8V = **536,4 V** → Faixa MPPT 460–800V ✅
- Tensão Voc string: 18 × 36,9V = **664,2 V** → Abaixo de 1000V máx ✅
- Corrente por MPPT (2 strings): 2 × 8,39A = **16,78 A** → Abaixo de 18,6A ✅

---

## Passo 7: Perdas

| Tipo de Perda | Valor Sugerido |
|---------------|----------------|
| Soiling (sujeira) | 2% |
| Mismatch | 1,5% |
| Perdas ôhmicas CC | 1,5% |
| Perdas ôhmicas CA | 0,5% |
| Degradação | 1% (sistema com ~1 ano em 2017) |
| Indisponibilidade | 0% |
| Sombreamento | Não configurar (carport sem obstruções) |

**IMPORTANTE:** Anotar EXATAMENTE os valores usados para replicar no SAM.

---

## Passo 8: Simular

1. Clicar em **Simulation > Run**
2. Verificar ausência de erros/warnings críticos

---

## Passo 9: Extrair Resultados

1. **Energia mensal injetada na rede (kWh)** — cada mês
2. **Energia anual total (kWh)**
3. **Performance Ratio (%)** — anual
4. **Yf — Produtividade Final (kWh/kWp)**
5. **Diagrama de perdas** (guardar imagem para o artigo)

---

## Passo 10: Exportar Dados Meteorológicos para o SAM

1. **Databases > Meteo tables and graphs**
2. Selecionar o site do Rio de Janeiro
3. **Export > Hourly file > formato SAM CSV**
4. Salvar (ex: "Meteonorm_RJ_SAM.csv")

---

## Checklist

- [ ] Localização: -22.86, -43.23, 11m
- [ ] Base meteorológica: Meteonorm
- [ ] Módulo: Kyocera KD250GH-4FB2 (250 Wp)
- [ ] Inversor: Kaco Powador 20TL3 (17 kW) × 6
- [ ] 396 módulos = 99 kWp
- [ ] Inclinação 10° / Azimute -46° (Noroeste)
- [ ] 18 módulos em série, 22 strings
- [ ] Perdas configuradas (anotar valores)
- [ ] Simulação executada sem erros
- [ ] Resultados mensais anotados
- [ ] Dados Meteonorm exportados para SAM
