# 🍽️ Computational Gastronomy: Network Analysis & Food Pairing

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=jupyter&logoColor=white)
![NetworkX](https://img.shields.io/badge/Library-NetworkX-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

> Un'analisi data-driven che esplora le differenze strutturali tra cucina tradizionale e d'avanguardia attraverso Network Science, con validazione chimica tramite il Flavor Network di Ahn et al. (2011).

---

## 📋 Panoramica del Progetto

Questo progetto applica la **Network Science** e tecniche di **Machine Learning** al dominio culinario per rispondere a una domanda di ricerca specifica:

**"La cucina d'avanguardia presenta proprietà Small-World più marcate rispetto alla cucina tradizionale?"**

L'analisi è strutturata su tre livelli complementari:

1. **Analisi Topologica:** Confronto statisticamente rigoroso tra reti culinarie tradizionali e innovative (El Celler de Can Roca - 3⭐ Michelin)
2. **Correzione Bias:** Bootstrap sampling per eliminare artefatti dovuti a dimensioni diverse delle reti
3. **Validazione Chimica:** Flavor Network basato su composti aromatici condivisi (dataset Ahn et al. 2011 - Nature Scientific Reports)

---

## 🔬 Analisi Svolte

### 1. Analisi Topologica con Bootstrap Sampling

**Dataset:**
- **Traditional Cuisine:** 315 ingredienti, 36,291 connessioni
- **El Celler de Can Roca:** 57 ingredienti, 642 connessioni

**Problema identificato:** Confronto diretto = bias dimensionale (ratio 5.5:1)

**Soluzione implementata:**
- 100 campioni bootstrap dalla rete tradizionale
- Ciascuno con esattamente 57 nodi (= dimensione Roca)
- Confronto distribuzione vs valore singolo
- Test statistico: Mann-Whitney U (p < 0.001)

**Metriche calcolate:**
- **Small-Worldness (σ):** Roca = 1.99 vs Traditional = 1.25 ± 0.12 (p < 0.001) ⭐
- **Modularity (Q):** Roca = 0.164 vs Traditional = 0.023 ± 0.013 (7x superiore!)
- **Clustering Coefficient:** Entrambe alte (>0.78)
- **Path Length:** Roca più alto (cammini più lunghi)
- **Centrality Measures:** Degree, Betweenness, Closeness, Eigenvector

**Risultato chiave:** La cucina d'avanguardia mostra proprietà small-world SIGNIFICATIVAMENTE più marcate e modularità maggiore, indicando una rete più compartimentata ma globalmente efficiente.

### 2. Flavor Network (Validazione Chimica)

Analisi basata sul dataset **Ahn et al. (2011)**:
- 1,531 ingredienti analizzati scientificamente
- 1,000+ composti volatili identificati
- 221,777 connessioni basate su composti aromatici condivisi

**Analisi cross-category:**
- Filtro intelligente per mostrare solo coppie di categorie diverse
- Top 15 abbinamenti cross-category con maggiore affinità chimica
- Validazione della Food Pairing Hypothesis

**Risultato:** Gli abbinamenti tradizionali classici (caffè-cioccolato, pomodoro-basilico) sono supportati da forte sovrapposizione di composti aromatici.

### 3. Bridge Discovery (Dual-Algorithm Approach)

Sistema interattivo per identificare ingredienti "ponte" tra coppie non ovvie:

**Due metodi complementari:**
1. **Betweenness Centrality:** Identifica gatekeeper strutturali nella rete
2. **Optimal Path Centrality:** Trova ponti lungo il percorso chimico più breve

**Case Studies inclusi:**
- **Beef & Wine:** Path length = 1 (validazione abbinamento tradizionale)
- **Chocolate & Vanilla:** Path length = 1 (affinità chimica diretta)
- **Salmon & Maple Syrup:** Path length = 2 (ponte = champagne wine) ⭐

**Scoperta chiave:**
- **Path = 1:** Abbinamenti tradizionali (validati chimicamente)
- **Path = 2-3:** Abbinamenti innovativi (richiedono creatività + ponti)

Il sistema identifica COME rendere possibili abbinamenti apparentemente incompatibili.

---

## 🛠️ Tecnologie Utilizzate

### Core Libraries
- **Python 3.x**
- **NetworkX:** Creazione e analisi grafi complessi, algoritmi di centralità, community detection
- **Pandas & NumPy:** Manipolazione dati, operazioni matriciali
- **Matplotlib & Seaborn:** Visualizzazione avanzata (heatmaps, distribuciones, grafici)
- **SciPy:** Test statistici (Mann-Whitney U)
- **Python-Louvain:** Community detection con algoritmo Louvain

### Algoritmi Implementati
- Bootstrap sampling (n=100)
- Small-worldness calculation (Watts-Strogatz)
- Modularity optimization
- Betweenness centrality (ottimizzato con subgraph limiting)
- Shortest path algorithms
- Statistical hypothesis testing

---

## 📊 Visualizzazioni Generate

Il progetto produce visualizzazioni scientifiche di alta qualità:

1. **Bootstrap Distribution Analysis:** 6-panel histogram comparison (sigma, clustering, modularity, path length, density, degree)
2. **Statistical Comparison Table:** Tabella formattata con risultati test Mann-Whitney U
3. **Cross-Category Flavor Pairs:** Bar chart top 15 abbinamenti inter-categoria
4. **Bootstrap Sampling Diagram:** Schema concettuale del processo di campionamento
5. **Network Topology Comparison:** Metriche comparative visuali

Tutte le visualizzazioni sono esportabili in alta risoluzione (300 DPI) per pubblicazioni.

---

## 📁 Struttura del Progetto

```
computational-gastronomy/
│
├── Computational_Gastronomy.ipynb          # Notebook Principale (EN)
├── Computational_Gastronomy_ITA.ipynb      # Notebook dettagliata (ITA)
├── requirements.txt                         # Dipendenza Python
├── Menu_Ingredienti_Completo.txt           # Dati sugli ingredienti
│
├── data/                                    # Cartella Dati
│   ├── adjacency_matrices/                 # Struttura Ricette
│   └── flavor_network/                     # Ahn et al. 2011 dataset
│
├── presentation/                            # Materiale presentazione
    ├── imgs/                                            
    └── Computational_GastronomyITA.pptx     # slide PowerPoint 
```

---

## 🚀 Come Eseguire il Progetto

### 1. Clona la repository
```bash
git clone https://github.com/felisariaurora/computational-gastronomy.git
cd computational-gastronomy
```

### 2. Installa le dipendenze
```bash
pip install -r requirements.txt
```

### 3. Download dei dataset
I dataset sono disponibili separatamente:
- **Recipe Networks:** Generati da ricette tradizionali e menu El Celler de Can Roca
- **Flavor Network:** Dataset Ahn et al. (2011) da [Nature Scientific Reports](https://doi.org/10.1038/srep00196)

Posiziona i file nella cartella `data/` come indicato nella struttura.

### 4. Avvia il Notebook
```bash
jupyter notebook Computational_Gastronomy.ipynb
```

### 5. Esegui l'analisi
Il notebook è strutturato in sezioni sequenziali:
1. Data Loading
2. Bootstrap Sampling
3. Topological Analysis
4. Flavor Network Analysis
5. Bridge Discovery
6. Interactive Exploration

---

## 📈 Risultati Chiave

### Ipotesi Confermata ✅
**La cucina d'avanguardia presenta topologia Small-World più marcata:**
- σ = 1.99 vs 1.25 (p < 0.001)
- Modularità 7x superiore
- Tutte le differenze statisticamente significative

### Scoperta Innovativa 🔬
**Path Length distingue tradizione da innovazione:**
- Path = 1 → Abbinamenti tradizionali (validati chimicamente)
- Path = 2-3 → Abbinamenti innovativi (richiedono ponti creativi)

**Esempio concreto:** Salmon + Maple Syrup funziona attraverso Wine come ponte chimico - validato nella cucina reale!

---

## 👤 Autore

**Aurora Felisari**
Laboratorio di Intelligenza Artificiale
Anno Accademico 2025/2026
Matricola: 397867

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Dataset Ahn et al. (2011) from Nature Scientific Reports
- El Celler de Can Roca for inspiring modernist cuisine data
- NetworkX development team for excellent graph analysis tools

---

*Progetto realizzato per il corso di Laboratorio di Algoritmi per l'Intelligenza Artificiale*

---
---

# 🇬🇧 Computational Gastronomy: Network Analysis & Food Pairing

> A data-driven analysis exploring structural differences between traditional and avant-garde cuisine through Network Science, with chemical validation via the Ahn et al. (2011) Flavor Network.

## 📋 Project Overview

This project applies **Network Science** and **Machine Learning** techniques to the culinary domain to answer a specific research question:

**"Does avant-garde cuisine exhibit more pronounced Small-World properties than traditional cuisine?"**

The analysis is structured across three complementary levels:

1. **Topological Analysis:** Statistically rigorous comparison between traditional and innovative culinary networks (El Celler de Can Roca - 3⭐ Michelin)
2. **Bias Correction:** Bootstrap sampling to eliminate artifacts due to different network sizes
3. **Chemical Validation:** Flavor Network based on shared aromatic compounds (Ahn et al. 2011 dataset - Nature Scientific Reports)

---

## 🔬 Key Analyses

### 1. Topological Analysis with Bootstrap Sampling

**Dataset:**
- **Traditional Cuisine:** 315 ingredients, 36,291 connections
- **El Celler de Can Roca:** 57 ingredients, 642 connections

**Identified problem:** Direct comparison = size bias (ratio 5.5:1)

**Implemented solution:**
- 100 bootstrap samples from traditional network
- Each with exactly 57 nodes (= Roca size)
- Distribution vs single value comparison
- Statistical test: Mann-Whitney U (p < 0.001)

**Calculated metrics:**
- **Small-Worldness (σ):** Roca = 1.99 vs Traditional = 1.25 ± 0.12 (p < 0.001) ⭐
- **Modularity (Q):** Roca = 0.164 vs Traditional = 0.023 ± 0.013 (7x higher!)
- **Clustering Coefficient:** Both high (>0.78)
- **Path Length:** Roca higher (longer paths)
- **Centrality Measures:** Degree, Betweenness, Closeness, Eigenvector

**Key result:** Avant-garde cuisine shows SIGNIFICANTLY more pronounced small-world properties and higher modularity, indicating a more compartmentalized yet globally efficient network.

### 2. Flavor Network (Chemical Validation)

Analysis based on **Ahn et al. (2011)** dataset:
- 1,531 scientifically analyzed ingredients
- 1,000+ identified volatile compounds
- 221,777 connections based on shared aromatic compounds

**Cross-category analysis:**
- Intelligent filtering to show only pairs from different categories
- Top 15 cross-category pairings with highest chemical affinity
- Validation of Food Pairing Hypothesis

**Result:** Classic traditional pairings (coffee-chocolate, tomato-basil) are supported by strong aromatic compound overlap.

### 3. Bridge Discovery (Dual-Algorithm Approach)

Interactive system to identify "bridge" ingredients between non-obvious pairs:

**Two complementary methods:**
1. **Betweenness Centrality:** Identifies structural gatekeepers in the network
2. **Optimal Path Centrality:** Finds bridges along the shortest chemical path

**Included Case Studies:**
- **Beef & Wine:** Path length = 1 (traditional pairing validation)
- **Chocolate & Vanilla:** Path length = 1 (direct chemical affinity)
- **Salmon & Maple Syrup:** Path length = 2 (bridge = champagne wine) ⭐

**Key discovery:**
- **Path = 1:** Traditional pairings (chemically validated)
- **Path = 2-3:** Innovative pairings (require creativity + bridges)

The system identifies HOW to make seemingly incompatible pairings work.

---

## 🛠️ Technologies Used

### Core Libraries
- **Python 3.x**
- **NetworkX:** Complex graph creation and analysis, centrality algorithms, community detection
- **Pandas & NumPy:** Data manipulation, matrix operations
- **Matplotlib & Seaborn:** Advanced visualization (heatmaps, distributions, plots)
- **SciPy:** Statistical tests (Mann-Whitney U)
- **Python-Louvain:** Community detection with Louvain algorithm

### Implemented Algorithms
- Bootstrap sampling (n=100)
- Small-worldness calculation (Watts-Strogatz)
- Modularity optimization
- Betweenness centrality (optimized with subgraph limiting)
- Shortest path algorithms
- Statistical hypothesis testing

---

## 📊 Generated Visualizations

The project produces high-quality scientific visualizations:

1. **Bootstrap Distribution Analysis:** 6-panel histogram comparison (sigma, clustering, modularity, path length, density, degree)
2. **Statistical Comparison Table:** Formatted table with Mann-Whitney U test results
3. **Cross-Category Flavor Pairs:** Bar chart of top 15 inter-category pairings
4. **Bootstrap Sampling Diagram:** Conceptual schema of sampling process
5. **Network Topology Comparison:** Visual comparative metrics

All visualizations are exportable in high resolution (300 DPI) for publications.

---

## 📁 Project Structure

```
computational-gastronomy/
│
├── Computational_Gastronomy.ipynb          # Main analysis notebook (EN)
├── Computational_Gastronomy_ITA.ipynb      # Italian version with detailed theory
├── requirements.txt                         # Python dependencies
├── Menu_Ingredienti_Completo.txt           # Ingredient data
│
├── data/                                    # Data folder
│   ├── adjacency_matrices/                 # Recipe networks
│   └── flavor_network/                     # Ahn et al. 2011 dataset
│
├── presentation/                            # Presentation materials
    ├── imgs/                                            
    └── Computational_GastronomyITA.pptx     # PowerPoint slides

```

---

## 🚀 How to Run the Project

### 1. Clone the repository
```bash
git clone https://github.com/felisariaurora/computational-gastronomy.git
cd computational-gastronomy
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Download datasets
Datasets are available separately:
- **Recipe Networks:** Generated from traditional recipes and El Celler de Can Roca menu
- **Flavor Network:** Ahn et al. (2011) dataset from [Nature Scientific Reports](https://doi.org/10.1038/srep00196)

Place files in the `data/` folder as indicated in the structure.

### 4. Launch the Notebook
```bash
jupyter notebook Computational_Gastronomy.ipynb
```

### 5. Run the analysis
The notebook is structured in sequential sections:
1. Data Loading
2. Bootstrap Sampling
3. Topological Analysis
4. Flavor Network Analysis
5. Bridge Discovery
6. Interactive Exploration

---

## 📈 Key Results

### Hypothesis Confirmed ✅
**Avant-garde cuisine exhibits more pronounced Small-World topology:**
- σ = 1.99 vs 1.25 (p < 0.001)
- Modularity 7x higher
- All differences statistically significant

### Innovative Discovery 🔬
**Path Length distinguishes tradition from innovation:**
- Path = 1 → Traditional pairings (chemically validated)
- Path = 2-3 → Innovative pairings (require creative bridges)

**Concrete example:** Salmon + Maple Syrup works through Wine as a chemical bridge - validated in real cuisine!

---
## 👤 Author

**Aurora Felisari**
Artificial Intelligence Laboratory
Academic Year 2025/2026
ID: 397867

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Ahn et al. (2011) dataset from Nature Scientific Reports
- El Celler de Can Roca for inspiring modernist cuisine data
- NetworkX development team for excellent graph analysis tools

---

*Project developed for the Artificial Intelligence Algorithms Laboratory course*
