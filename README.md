# Deep Learning Multi-Modale avec PyTorch

## ✨ Description du Projet
Ce projet acad99mique complet explore l'impl99mentation, l'entra99nement et l'analyse critique de mod88les de Deep Learning pour trois types de donn99es distincts :
1.  **Donn99es Tabulaires (MLP) :** Classification binaire sur le dataset *Breast Cancer Wisconsin*.
2.  **Vision par Ordinateur (CNN) :** Classification d'images sur le dataset *Fashion-MNIST*.
3.  **Traitement de S99quences (RNN/LSTM/GRU) :** Analyse de sentiment sur le dataset *IMDB Movie Reviews*.

## Ὠ0 Technologies Utilis99es
*   **Framework Principal :** PyTorch
*   **Traitement de Donn99es :** Pandas, Numpy, Scikit-Learn
*   **Visualisation :** Matplotlib, Seaborn
*   **NLP :** TorchText
*   **Environnement :** Google Colab (Support GPU/CUDA)

## Ἵ7 Architectures Impl99ment99es
### Partie I : MLP (Multi-Layer Perceptron)
*   Architecture 80 3 couches cach99es avec **Batch Normalization** et **Dropout**.
*   Comparaison rigoureuse des strat99gies d'initialisation des poids : **Xavier (Glorot)**, **Gaussienne** et **Constante (Z99ro)**.
*   Utilisation d'un m99canisme d'**Early Stopping** pour pr99venir le surapprentissage.

### Partie II : CNN (Convolutional Neural Networks)
*   Impl99mentation d'une architecture de type **LeNet-5**.
*   99tude exp99rimentale comparant 5 configurations (variation des filtres, taux d'apprentissage et r99gularisation).
*   Analyse visuelle : extraction des **Feature Maps** et des noyaux de convolution pour interpr99ter les filtres appris.

### Partie III : Mod88les S99quentiels (RNN, LSTM, GRU)
*   Pipeline de pr99traitement textuel complet (Tokenisation, construction de vocabulaire, Padding).
*   Comparaison des performances entre les cellules r99currentes simples et les architectures 80 portes (LSTM/GRU) pour r99soudre le probl88me de disparition du gradient.

## ὄA R99sultats Cl99s
*   **Initialisation :** L'initialisation Xavier s'est montr99e sup99rieure pour stabiliser la convergence d88s les premi88res 99poques.
*   **Efficacit99 spatiale :** Le CNN a surpass99 le MLP sur les images en utilisant moins de param88tres gr80ce au partage des poids et 80 la localit99 des filtres.
*   **M99moire s99quentielle :** Le LSTM et le GRU ont d99montr99 une meilleure capacit99 80 capturer les d99pendances 80 long terme dans les critiques de films par rapport au RNN simple.

## Ὄ2 Contenu du Rapport
L'archive g99n99r99e par le notebook (`rapport_visualisations_complet.zip`) contient :
*   Les courbes de perte et d'accuracy.
*   Les matrices de confusion finales pour chaque mod88le.
*   Les visualisations des filtres de convolution.
*   Les courbes ROC/AUC.