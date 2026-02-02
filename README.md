# 🥗 Computational Gastronomy: Network Analysis & Food Pairing

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=jupyter&logoColor=white)
![NetworkX](https://img.shields.io/badge/Library-NetworkX-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

> Un'analisi data-driven che esplora le differenze strutturali tra cucina tradizionale e molecolare e visualizza le reti chimiche del Food Pairing.

---

## 📋 Panoramica del Progetto
Questo progetto applica la **Teoria dei Grafi** (Network Analysis) e la **Data Science** al dominio culinario. L'obiettivo è duplice:
1.  **Confronto Topologico:** Analizzare come la struttura delle ricette cambia dalla cucina tradizionale a quella modernista (El Celler de Can Roca).
2.  **Analisi Chimica (Flavor Network):** Investigare l'ipotesi del *Food Pairing*, costruendo reti basate sui composti aromatici condivisi tra gli ingredienti.

## 🔬 Analisi Svolte

### 1. Analisi Topologica (Ricette)
Confronto tra due dataset principali: **Traditional Recipes (Ctrad)** vs **Molecular Cuisine (Roca)**.
* **Metriche Calcolate:** Densità, Modularità, Distribuzione dei Gradi.
* **Insight:** La cucina moderna mostra una modularità inferiore, indicando una rottura delle barriere tradizionali tra categorie di ingredienti (es. dolce/salato).

### 2. Flavor Network (Chimica)
Analisi basata sui composti volatili condivisi.
* **Community Detection:** Identificazione di cluster di ingredienti chimicamente simili.
* **Hub Identification:** Individuazione degli ingredienti "ponte" (es. Tè nero, Arrosto, Birra) che collegano categorie diverse grazie alla loro complessità molecolare.
* **Heatmap delle Categorie:** Visualizzazione delle affinità chimiche tra intere famiglie di cibi (es. Frutta & Erbe).

## 🛠️ Tecnologie Utilizzate
* **Python 3.x**
* **NetworkX:** Per la creazione e analisi dei grafi complessi.
* **Pandas & NumPy:** Per la manipolazione dei dati.
* **Matplotlib & Seaborn:** Per la visualizzazione dati avanzata (Heatmaps, Ego-Graphs).

## 📊 Visualizzazioni
Il notebook produce diverse visualizzazioni avanzate, tra cui:
* **Ego-Graphs:** Focus su singoli ingredienti (Case Studies) per mostrare i loro abbinamenti chimici migliori.
* **Cluster Maps:** Mappe colorate delle comunità di ingredienti.
* **Heatmaps:** Matrici di adiacenza pesate per categorie alimentari.

## 🚀 Come Eseguire il Progetto
1.  Clona la repository:
    ```bash
    git clone [https://github.com/tuo-username/computational-gastronomy.git](https://github.com/felisariaurora/computational-gastronomy.git)
    ```
2.  Installa le dipendenze:
    ```bash
    pip install pandas networkx matplotlib seaborn
    ```
3.  Avvia il Notebook:
    ```bash
    jupyter notebook main_analysis.ipynb
    ```

---
*Progetto realizzato per il corso di Laboratorio di Algoritmi per l'Intelligenza Artificiale - Anno Accademico 2025/2026*

---
---

# 🇬🇧 Computational Gastronomy: Network Analysis & Food Pairing

> A data-driven analysis exploring structural differences between traditional and molecular cuisine, visualizing chemical Food Pairing networks.

## 📋 Project Overview
This project applies **Graph Theory** (Network Analysis) and **Data Science** to the culinary domain. The dual objective is:
1.  **Topological Comparison:** Analyzing how recipe structure evolves from traditional to modernist cuisine (El Celler de Can Roca).
2.  **Chemical Analysis (Flavor Network):** Investigating the *Food Pairing hypothesis* by building networks based on shared aromatic compounds between ingredients.

## 🔬 Key Analyses

### 1. Topological Analysis (Recipes)
Comparison between two main datasets: **Traditional Recipes (Ctrad)** vs **Molecular Cuisine (Roca)**.
* **Metrics:** Density, Modularity, Degree Distribution.
* **Key Insight:** Modern cuisine exhibits lower modularity, indicating a breakdown of traditional boundaries between ingredient categories (e.g., savory/sweet).

### 2. Flavor Network (Chemistry)
Analysis based on shared volatile compounds.
* **Community Detection:** Identifying clusters of chemically similar ingredients.
* **Hub Identification:** Pinpointing "bridge" ingredients (e.g., Black Tea, Roasted Beef, Beer) that connect diverse categories due to molecular complexity.
* **Category Heatmap:** Visualizing chemical affinities between entire food families (e.g., Fruit & Herbs).

## 🛠️ Tech Stack
* **Python 3.x**
* **NetworkX:** For complex graph creation and analysis.
* **Pandas & NumPy:** For data manipulation.
* **Matplotlib & Seaborn:** For advanced data visualization (Heatmaps, Ego-Graphs).

## 📊 Visualizations
The notebook generates several advanced visualizations, including:
* **Ego-Graphs:** Focus on single ingredients (Case Studies) to showcase their best chemical pairings.
* **Cluster Maps:** Colored maps of ingredient communities.
* **Heatmaps:** Weighted adjacency matrices for food categories.

## 🚀 How to Run
1.  Clone the repository:
    ```bash
    git clone [https://github.com/your-username/computational-gastronomy.git](https://github.com/felisariaurora/computational-gastronomy.git)
    ```
2.  Install dependencies:
    ```bash
    pip install pandas networkx matplotlib seaborn
    ```
3.  Launch the Notebook:
    ```bash
    jupyter notebook main_analysis.ipynb
    ```
