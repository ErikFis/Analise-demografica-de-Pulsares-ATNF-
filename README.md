# Data Science em Astrofísica: Demografia de Pulsares

Este repositório é um projeto de Ciência de Dados e Engenharia de Dados que constrói uma infraestrutura completa de ingestão, tratamento e análise exploratória (EDA) de dados observacionais de estrelas de nêutrons, consumindo o Catálogo de Pulsares do ATNF (Australia Telescope National Facility).

O foco deste projeto é a exploração das propriedades físicas das estrelas de nêutrons, como período de rotação, campo magnético superficial e idades características e a identificação de subpopulações e aglomerados globulares.

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
│   ├── raw/                 # Dados brutos extraídos diretamente do ATNF (atnf_raw_arquivos)
│   ├── interim/             # Dados intermediários de processamento
│   └── processed/           # Dados limpos e categorizados (catalog_categorized.csv)
├── notebooks/
│   ├── 01_data_exploration/    # Ingestão do catálogo, dados faltantes e mapa galáctico bruto
│   ├── 02_statistical_analysis/# Análise estatística, diagrama P-Pdot e busca por aglomerados
│   └── 03_data_categorization/ # Pipeline final de categorização e exportação dos dados
├── figures/                 # Gráficos gerados pelas análises (Diagramas P-Pdot, Mapas Galácticos)
└── README.md
```

---

## Principais Análises e Notebooks

### 1. Ingestão e Exploração Inicial (`01_catalog_exploration.ipynb`)
- Download automatizado do catálogo observacional do ATNF via `psrqpy`.
- Inspeção da qualidade dos dados e cálculo de percentuais de valores nulos por coluna.
- Visualização preliminar da distribuição espacial bruta no céu em coordenadas galácticas.

### 2. Análise Estatística e Estrutura da População (`02_statistical_analysis.ipynb`)
- **Categorização da População**: Regras heurísticas e físicas para consolidação da coluna `TYPE`:
  - **Pulsares Normais**: População do disco galáctico.
  - **MSP (Millisecond Pulsars)**: Inferidos fisicamente via Período de Rotação ($P < 30$ ms).
  - **Magnetares (AXP/SGR)**: Campos magnéticos extremos ($> 10^{14}$ Gauss).
  - **RRAT, XINS, HE, NRAD**: Classes exóticas e subpopulações com emissões específicas.
- **O Diagrama $P - \dot{P}$**: Visualização equivalente ao Diagrama HR para estrelas de nêutrons, destacando ilhas evolutivas de MSPs e Magnetares.
- **Mapeamento Galáctico e Aglomerados Globulares**: 
  - Mapeamento em projeção de Mollweide em coordenadas galácticas ($l, b$).
  - Identificação e filtro de aglomerados globulares densos: **47 Tucanae (NGC 104)**, **M15**, **NGC 1851** e **NGC 6752**.
  - Separação de fontes extragalácticas (**Nuvens de Magalhães - SMC / LMC**), que aparecem sobrepostas visualmente em projeção 2D.

### 3. Pipeline de Categorização (`03_categorization.ipynb`)
- Execução do pré-processamento estruturado.
- Salvamento do catálogo rotulado em `data/processed/catalog_categorized.csv` para consumo seguro em etapas futuras de Machine Learning.

---

## Como Executar

1. Clone o repositório:
```bash
git clone https://github.com/ErikFis/Analise-demografica-de-Pulsares-ATNF-.git
cd Analise-demografica-de-Pulsares-ATNF-
```

2. Crie um ambiente conda e instale as dependências:
```bash
conda create -n neutron-stars python=3.11
conda activate neutron-stars
pip install psrqpy pandas numpy matplotlib astropy jupyter
```

3. Abra os notebooks:
```bash
jupyter notebook
```
Explore a pasta `notebooks/` sequencialmente.

---

## Licença

Este projeto é de código aberto. Sinta-se livre para utilizar, modificar e distribuir conforme necessário.
