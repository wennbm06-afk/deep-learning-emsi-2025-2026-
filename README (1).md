# Projet de Fin de Module — Deep Learning (EMSI Casablanca, 2025-2026)

## 📌 Idée générale du projet

Ce repository contient l'ensemble des travaux réalisés dans le cadre du projet de fin de module **Deep Learning** à l'EMSI Casablanca. Le projet vise à concevoir, implémenter et comparer plusieurs familles d'architectures de deep learning sous **PyTorch**, en les adaptant à trois types de structures de données distinctes :

| Partie | Type de données | Architecture | Dataset |
|---|---|---|---|
| **I** | Tabulaire | MLP (Perceptron multicouche) | Breast Cancer Wisconsin |
| **II** | Image | CNN (inspiré de LeNet) | Fashion-MNIST |
| **III** | Séquentielle / Texte | RNN, LSTM, GRU, Seq2Seq | Corpus textuel (traduction / modélisation de langage) |

Pour chaque partie, le travail couvre :
- une étude théorique des concepts fondamentaux,
- une implémentation complète sous PyTorch,
- une étude expérimentale comparative (hyperparamètres, architectures),
- une analyse critique des résultats,
- une question de synthèse sur le dataset réel utilisé.

Une discussion transversale finale relie les trois approches en expliquant pourquoi un même paradigme d'apprentissage supervisé doit être décliné différemment selon la géométrie, la dépendance locale, la temporalité et la représentation des données.

---

## 📁 Structure des dossiers et fichiers

```
deep-learning-emsi-2025-2026/
│
├── README.md                          → ce fichier
├── .gitignore                         → fichiers/dossiers exclus du suivi Git
├── .gitattributes                     → configuration Git LFS (fichiers lourds)
├── requirements.txt                   → dépendances Python du projet
│
├── partie1_mlp/                       → Partie I : MLP sur données tabulaires
│   ├── notebook_mlp.ipynb             → notebook complet (théorie, code, résultats)
│   ├── best_mlp.pth                   → poids du meilleur modèle entraîné
│   └── figures/                       → visualisations générées (courbes, matrices, etc.)
│
├── partie2_cnn/                       → Partie II : CNN sur données images
│   ├── notebook_cnn.ipynb             → notebook complet (théorie, code, résultats)
│   ├── best_cnn.pth                   → poids du meilleur modèle entraîné
│   └── figures/                       → visualisations générées (feature maps, etc.)
│
├── partie3_rnn_seq2seq/               → Partie III : RNN/LSTM/GRU/Seq2Seq
│   ├── notebook_rnn_lstm_gru.ipynb    → comparaison RNN simple / LSTM / GRU
│   ├── notebook_seq2seq.ipynb         → système encodeur-décodeur (traduction)
│   └── figures/                       → courbes de perplexité, comparaisons, etc.
│
├── rapport/                           → Rapport scientifique final
│   ├── rapport.tex                    → code source LaTeX (Overleaf)
│   ├── rapport.pdf                    → version PDF compilée du rapport
│   └── figures/                       → figures centralisées utilisées dans le rapport
│
└── docs/                              → Documents annexes
    └── enonce_projet.pdf              → énoncé original du projet (EMSI)
```

---

## 🚀 Comment exécuter le projet

### Prérequis

- Python 3.9+
- Un environnement Jupyter (Jupyter Notebook, JupyterLab) ou Google Colab
- (Optionnel) GPU compatible CUDA pour accélérer l'entraînement

### Installation des dépendances

```bash
pip install -r requirements.txt
```

### Exécution des notebooks

Chaque notebook est autonome et peut être exécuté indépendamment :

```bash
jupyter notebook partie1_mlp/notebook_mlp.ipynb
jupyter notebook partie2_cnn/notebook_cnn.ipynb
jupyter notebook partie3_rnn_seq2seq/notebook_rnn_lstm_gru.ipynb
jupyter notebook partie3_rnn_seq2seq/notebook_seq2seq.ipynb
```

> 💡 Les notebooks peuvent également être ouverts directement dans **Google Colab** en les important depuis ce repository GitHub.

### Fichiers de poids des modèles

Les fichiers `.pth` contiennent les poids des meilleurs modèles entraînés et sont gérés via **Git LFS** en raison de leur taille. Assurez-vous d'avoir Git LFS installé avant de cloner :

```bash
git lfs install
git clone https://github.com/TON_USERNAME/deep-learning-emsi-2025-2026.git
```

---

## 📊 Rapport scientifique

Le rapport complet (introduction, méthodologie, implémentation, résultats, interprétation, limites et conclusion) est disponible :
- en version source LaTeX : [`rapport/rapport.tex`](rapport/rapport.tex)
- en version PDF compilée : [`rapport/rapport.pdf`](rapport/rapport.pdf)

---

## 🛠️ Technologies utilisées

- **PyTorch** — implémentation des modèles de deep learning
- **scikit-learn** — préparation des données et métriques d'évaluation
- **Matplotlib / Seaborn** — visualisations et courbes
- **NLTK** — évaluation BLEU (Partie III)
- **LaTeX (Overleaf)** — rédaction du rapport scientifique

---

## 👤 Auteur

Projet réalisé individuellement dans le cadre du module **Deep Learning** — Filière Informatique, EMSI Casablanca, année universitaire 2025-2026.
