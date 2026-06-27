Projet de Fin de Module — Deep Learning (EMSI Casablanca, 2025-2026)

📌 Idée générale du projet

Ce repository contient l'ensemble des travaux réalisés dans le cadre du projet de fin de module Deep Learning à l'EMSI Casablanca. Le projet vise à concevoir, implémenter et comparer plusieurs familles d'architectures de deep learning sous PyTorch, en les adaptant à trois types de structures de données distinctes :

PartieType de donnéesArchitectureDatasetRésultat cléITabulaireMLP (Sequential + classe personnalisée)Breast Cancer WisconsinAccuracy 97,67 % · AUC 0,9959IIImageCNN (LeNet-Moderne) vs MLP baselineFashion-MNISTCNN 90,64 % vs MLP 87,87 %IIISéquentielle / TexteSeq2Seq (LSTM bidirectionnel + attention Bahdanau)Tatoeba (fra-eng, 30k paires)Entraînement non finalisé (limite assumée)

Pour chaque partie, le travail couvre :


une étude théorique des concepts fondamentaux,
une implémentation complète sous PyTorch,
une étude expérimentale comparative (stratégies d'initialisation, étude d'ablation architecturale, comparaison de cellules récurrentes),
une analyse critique honnête des résultats, y compris de leurs limites,
une question de synthèse sur le dataset réel utilisé.


Une discussion transversale finale relie les trois approches en expliquant pourquoi un même paradigme d'apprentissage supervisé doit être décliné différemment selon la géométrie, la dépendance locale, la temporalité et la représentation des données.


Note de transparence scientifique : la Partie III (système de traduction Seq2Seq) n'a pas pu être entraînée jusqu'à convergence dans le temps disponible, en raison du coût de calcul de l'architecture (LSTM bidirectionnel + attention). Cette limite est explicitement assumée et discutée dans le rapport plutôt que masquée par des résultats fabriqués.




📁 Structure des dossiers et fichiers

deep-learning-emsi-2025-2026/
│
├── README.md                          → ce fichier
├── .gitignore                         → fichiers/dossiers exclus du suivi Git
├── .gitattributes                     → configuration Git LFS (fichiers lourds)
├── requirements.txt                   → dépendances Python du projet
│
├── partie1_mlp/                       → Partie I : MLP sur données tabulaires
│   ├── notebook_mlp.ipynb             → notebook complet (théorie, code, résultats)
│   ├── best_mlp_model.pth             → poids du meilleur modèle (init Xavier)
│   └── figures/
│       ├── data_exploration.png       → distribution des classes + top features
│       ├── learning_curves.png        → comparaison des stratégies d'initialisation
│       ├── init_weights.png           → distribution des poids selon l'initialisation
│       ├── confusion_matrix.png       → matrice de confusion (test set)
│       └── roc_curve.png              → courbe ROC (AUC = 0,9959)
│
├── partie2_cnn/                       → Partie II : CNN sur données images
│   ├── notebook_cnn.ipynb             → notebook complet (théorie, code, résultats)
│   ├── best_cnn_model.pth             → poids du modèle LeNet-Moderne
│   └── figures/
│       ├── dataset_samples.png        → exemples Fashion-MNIST par classe
│       ├── kernel_effects.png         → effets de noyaux de convolution manuels
│       ├── arch_comparison.png        → étude d'ablation (pooling, conv 1x1, filtres)
│       ├── feature_maps.png           → cartes de caractéristiques (Conv1/Conv2)
│       ├── mlp_vs_cnn_curves.png      → courbes d'apprentissage comparées
│       └── mlp_vs_cnn_confusion.png   → matrices de confusion comparées
│
├── partie3_seq2seq/                   → Partie III : Seq2Seq avec attention
│   ├── notebook_seq2seq.ipynb         → notebook (théorie, code, entraînement)
│   └── figures/
│       └── loss_plot_partie3.png      → courbe de perte (entraînement partiel)
│


🚀 Comment exécuter le projet

Prérequis


Python 3.9+
Un environnement Jupyter (Jupyter Notebook, JupyterLab) ou Google Colab
(Optionnel) GPU compatible CUDA pour accélérer l'entraînement — fortement recommandé pour la Partie III


Installation des dépendances

bashpip install -r requirements.txt
python -m spacy download en_core_web_sm
python -m spacy download fr_core_news_sm

Exécution des notebooks

Chaque notebook est autonome et peut être exécuté indépendamment :

bashjupyter notebook partie1_mlp/notebook_mlp.ipynb
jupyter notebook partie2_cnn/notebook_cnn.ipynb
jupyter notebook partie3_seq2seq/notebook_seq2seq.ipynb


💡 Les notebooks peuvent également être ouverts directement dans Google Colab en les important depuis ce repository GitHub. La Partie III nécessite un GPU pour un entraînement dans un temps raisonnable.



Fichiers de poids des modèles

Les fichiers .pth contiennent les poids des modèles entraînés et sont gérés via Git LFS en raison de leur taille. Assurez-vous d'avoir Git LFS installé avant de cloner :

bashgit lfs install
git clone https://github.com/TON_USERNAME/deep-learning-emsi-2025-2026.git


📊 Résultats détaillés

Partie I — MLP (Breast Cancer Wisconsin)


Accuracy : 0,9767 · Precision : 0,9643 · Recall : 1,0000 · F1-score : 0,9818 · AUC-ROC : 0,9959
0 faux négatif sur l'ensemble de test (critique en contexte médical)
L'initialisation constante des poids est pathologique (accuracy bloquée à ~0,625) ; Xavier et Gaussienne convergent toutes deux correctement


Partie II — CNN vs MLP (Fashion-MNIST)


CNN LeNet-Moderne : 0,9064 (3 époques) · MLP baseline : 0,8787 (25 époques)
Le max-pooling surpasse l'average-pooling dans l'étude d'ablation
Classe la plus difficile pour les deux modèles : « Chemise » (confondue avec T-shirt/Pull)


Partie III — Seq2Seq avec attention (Tatoeba fra-eng)


Architecture conçue et implémentée : encodeur LSTM bidirectionnel + attention Bahdanau + décodeur LSTM
⚠️ Entraînement complet interrompu pour raisons de ressources de calcul ; la courbe fournie correspond à un entraînement de secours sur modèle allégé (2 époques), non représentatif de la performance finale visée
La discussion théorique (RNN vs LSTM vs GRU, intérêt de l'attention) reste intégralement développée dans le rapport



📄 Rapport scientifique

Le rapport complet (introduction, méthodologie, implémentation, résultats, interprétation, limites et conclusion) est disponible :


en version source LaTeX : rapport/rapport.tex
en version PDF compilée : rapport/rapport.pdf



🛠️ Technologies utilisées


PyTorch — implémentation des modèles de deep learning
scikit-learn — préparation des données et métriques d'évaluation
spaCy — tokenisation anglais/français (Partie III)
Matplotlib / Seaborn — visualisations et courbes
NLTK — évaluation BLEU (Partie III)
LaTeX (Overleaf) — rédaction du rapport scientifique



👤 Auteur

Projet réalisé individuellement par Bouka Wenn dans le cadre du module Deep Learning — Filière Informatique, EMSI Casablanca, année universitaire 2025-2026.
