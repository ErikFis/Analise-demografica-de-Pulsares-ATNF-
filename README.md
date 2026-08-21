# Data Science em Astrofísica: Demografia de Pulsares

Este repositório é um **projeto de Ciência de Dados e Engenharia de Dados** que constrói uma infraestrutura completa de ingestão, tratamento e análise exploratória (EDA) de dados observacionais de estrelas de nêutrons, consumindo o **Catálogo de Pulsares do ATNF (Australia Telescope National Facility)**. 

O foco deste projeto é a exploração das propriedades físicas das estrelas de nêutrons — como período de rotação, campo magnético superficial e idades características — e a identificação de subpopulações e aglomerados globulares.

---

## Objetivos do Projeto

1. **Tratamento de Dados do ATNF:** Automatizar o download, limpeza e categorização dos dados brutos do ATNF, focando nos parâmetros físicos relevantes.
2. **Análise Estatística da População:** Explorar as distribuições (bimodais) de pulsares normais, milissegundo pulsares (MSPs), magnetares e outras classes exóticas.
3. **Física dos Parâmetros:** Analisar e visualizar a física intrínseca dessas estrelas através do clássico diagrama $P - \dot{P}$ (Período vs. Derivada do Período).
4. **Mapeamento de Aglomerados:** Mapear a distribuição galáctica (coordenadas $l, b$) para identificar aglomerados globulares (ex: 47 Tucanae) e separar fontes extragalácticas (Nuvens de Magalhães).

---

## Estrutura do Repositório

```text
.
├── data/
│   ├── raw/             # Dados brutos extraídos diretamente do ATNF (imutáveis)
│   └── interim/         # Dados limpos e categorizados (catalog_categorized.csv)
├── notebooks/
│   ├── 01_data_exploration/    # Download e exploração inicial do catálogo
│   ├── 02_sky_map/             # Explorações de mapas do céu (rascunhos)
│   └── 03_statistical_analysis/# Análise estatística completa, gráficos e descoberta de aglomerados
├── figures/             # Gráficos gerados pelas análises (Diagramas P-Pdot, Mapas Galácticos)
└── .gitignore
```

---

## Principais Análises

As análises estatísticas e físicas podem ser encontradas em [`notebooks/03_statistical_analysis/03_statistical_analysis.ipynb`](notebooks/03_statistical_analysis/03_statistical_analysis.ipynb), onde abordamos:

### 1. Categorização da População
As estrelas de nêutrons foram categorizadas de acordo com suas propriedades físicas e de emissão:
- **Pulsares Normais**: População jovem/média do disco galáctico.
- **MSP (Millisecond Pulsars)**: Pulsares velhos "reciclados" com altas velocidades de rotação ($P < 30$ ms).
- **Magnetares (AXP/SGR)**: Campos magnéticos extremos ($> 10^{14}$ Gauss).
- **RRAT, XINS, HE, NRAD**: Outras classes exóticas e subpopulações isoladas.

### 2. O Diagrama $P - \dot{P}$
Construímos o diagrama $P - \dot{P}$, o equivalente ao Diagrama HR para estrelas de nêutrons, ilustrando as "ilhas" de MSPs, a nuvem principal de pulsares de rádio e a posição isolada dos magnetares. A partir destas duas variáveis ($P$ e $\dot{P}$), derivamos o Campo Magnético Superficial ($B$) e a Idade Característica ($\tau$).

### 3. Mapeamento Galáctico e Aglomerados Globulares
A distribuição das estrelas no céu (projeção de Mollweide) revela um alinhamento claro com o plano galáctico, mas também subestruturas notáveis:
- **Aglomerados Globulares**: Identificamos concentrações densas de MSPs em locais como **47 Tucanae (NGC 104)**, **M15**, **NGC 1851** e **NGC 6752**.
- **Fontes Extragalácticas**: Separamos visualmente fontes localizadas nas **Pequena e Grande Nuvens de Magalhães (SMC / LMC)**, que se sobrepõem visualmente ao aglomerado 47 Tuc devido à projeção 2D do céu.

---

## Como Executar

O projeto utiliza a biblioteca `psrqpy` para ingestão dos dados. 

1. Clone o repositório:
```bash
git clone https://github.com/SEU-USUARIO/demografia-de-pulsares.git
cd demografia-de-pulsares
```

2. Crie um ambiente conda e instale as dependências:
```bash
conda create -n neutron-stars python=3.11
conda activate neutron-stars
pip install psrqpy pandas numpy matplotlib jupyter
```

3. Abra os notebooks:
```bash
jupyter notebook
```
Explore a pasta `notebooks/` sequencialmente.

---

## Licença
Este projeto é de código aberto. Sinta-se livre para utilizar, modificar e distribuir conforme necessário.
