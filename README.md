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
