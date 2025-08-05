# **SP Housing Affordability Study**  
**Análise da acessibilidade habitacional e dinâmicas de gentrificação na cidade de São Paulo**  

---

## 🏙️ **Visão Geral**  
Este projeto investiga os padrões de acessibilidade habitacional e processos de gentrificação em São Paulo através de:  

- **Análise espacial** da evolução dos preços de imóveis (2010-2023)  
- **Cálculo de indicadores** de acessibilidade (razão preço/renda, custo transporte-moradia)  
- **Mapeamento de áreas em gentrificação** usando dados de:  
  - Valorização imobiliária  
  - Mudança no perfil socioeconômico  
  - Oferta de serviços urbanos  
- **Identificação de "deslocamentos populacionais"** causados por pressão imobiliária  

---

## 📊 **Fontes de Dados Principais**  

| Categoria               | Fontes                                                                 | Variáveis Chave |
|-------------------------|-----------------------------------------------------------------------|----------------|
| **Mercado Imobiliário** | [ZAP Imóveis API](https://www.zapimoveis.com.br/), [SECOVI-SP](https://secovi.com.br/) | Preço/m², localização, tipo de imóvel |
| **Socioeconômicas**     | [IBGE Censo](https://censo2022.ibge.gov.br/), [SEADE](https://www.seade.gov.br/) | Renda média, escolaridade |
| **Infraestrutura**      | [GeoSampa](http://geosampa.prefeitura.sp.gov.br/), [OpenStreetMap](https://www.openstreetmap.org/) | Proximidade a metrô, equipamentos urbanos |
| **Regulação Urbana**    | [PMSP - Planos Diretores](https://www.prefeitura.sp.gov.br/cidade/secretarias/desenvolvimento_urbano/) | Zonas de ZEIS, perímetros de intervenção |

---

## 🛠️ **Metodologia**  

### **1. Índices Calculados**  
- **Razão Preço-Renda** (anos de renda para comprar imóvel médio)  
- **Housing Affordability Index** (HAI) - metodologia ONU-Habitat  
- **Análise de Cluster** para identificar padrões territoriais  

### **2. Detecção de Gentrificação**  
```python
# Exemplo: Identificação de áreas com valorização acima da média
gentrification_zones = (
    df[(df['price_growth'] > df['city_avg']*1.5) & 
    (df['income_growth'] < df['city_avg']*0.7)
)
```

### **3. Ferramentas**  
- **Python**: Pandas, GeoPandas, Scikit-learn  
- **Sistemas de Informação Geográfica**: QGIS, Kepler.gl  
- **Análise Estatística**: Spatial Lag Models, Moran's I  

---

## 📂 **Estrutura do Projeto**  

```
sp-housing-affordability-study/  
├── data/  
│   ├── real_estate/        # Dados de preços por bairro (2010-2023)  
│   ├── census/             # Dados socioeconômicos  
│   └── urban_policy/       # Leis e zoneamentos  
├── notebooks/  
│   ├── 1_Data_Integration.ipynb  
│   ├── 2_Gentrification_Detection.ipynb  
│   └── 3_Policy_Simulations.ipynb  
├── reports/  
│   ├── affordability_maps/ # Mapas interativos  
│   └── policy_briefs/      # Recomendações  
└── src/  
    ├── spatial_analysis.py # Autocorrelação espacial  
    └── affordability.py   # Cálculo de índices  
```

---

## 📌 **Principais Resultados**  

### **Hotspots de Inacessibilidade**  
- Centro expandido: Razão preço/renda > 12 anos  
- Periferia: Custo transporte-moradia consome >45% da renda  

### **Áreas em Gentrificação Acelerada**  
1. **Vila Leopoldina** (valorização de 210% em 10 anos)  
2. **Brás** (mudança no perfil comercial/residencial)  
3. **Vila Madalena** (deslocamento de população de baixa renda)  

---

## 🚀 **Como Utilizar**  

1. **Instalação**:  
   ```bash  
   conda env create -f environment.yml  
   jupyter lab  
   ```  

2. **Gerar Mapas**:  
   ```bash  
   python src/visualization/map_gentrification.py --year=2023  
   ```  

---

## 🤝 **Contribuições**  
- [ ] Adicionar dados de aluguel (QuintoAndar)  
- [ ] Integrar com dados de cortiços e habitação informal  
- [ ] Desenvolver modelo preditivo de valorização  

---

## ⚖️ **Licença**  
CC-BY-SA 4.0 - **Requisito: citar fonte original**  

---

## ✉️ **Contato**  
**Observatório da Moradia SP** - moradia.sp@research.org  

🌍 **Acesso aos Dados**: [https://github.com/seu-usuario/sp-housing-affordability-study](https://github.com/seu-usuario/sp-housing-affordability-study)  

---  

**Dados para uma São Paulo mais justa e inclusiva!** 🏘️📊