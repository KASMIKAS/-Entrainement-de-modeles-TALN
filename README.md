# Entrainement de modèles de classification textuelle

Ce projet présente un travail sur l'entraînement de classifieurs textuels, utilisant des embeddings de mots pour représenter le contenu d'un texte, avec trois approches :

1. **Embeddings statiques** pré-calculés (type word2vec, glove)
2. Embeddings entraînés de zéro en même temps que le modèle de classification
3. Modèles contextuels pré-entraînés (type Bert/GPT)

Le notebook principal de ce dépôt est : **TP2_M2IAFA_TAL_2425_SUJET_.ipynb**.

## Jeu de données

Le travail se concentre sur une tâche de classification de sentiments, avec le jeu de données IMDB, accessible ici : https://huggingface.co/datasets/stanfordnlp/imdb

Pour accélérer l'expérimentation, seule une sous-partie du jeu de données train est utilisée, et le jeu de test est conservé pour évaluation.

## Approche Embeddings statiques pré-calculés (GloVe)

- Utilisation de la bibliothèque `gensim`, notamment le modèle `glove-wiki-gigaword-100` pour les embeddings de mots.
- Encodage des phrases par la moyenne des embeddings des mots présents dans la phrase (après suppression de la ponctuation).
- Création de fonctions pour encoder le dataset en vecteurs pour chaque phrase et extraction des labels associés.

## Traitement des données

- Téléchargement du dataset IMDB via la bibliothèque `datasets`.
- Extraction de 2 listes : une de vecteurs représentant les phrases, une des labels associés.

## Modélisation

- Proposition d’entraîner un classifieur simple (par exemple une régression logistique ou un MLP simple de `scikit-learn`) sur les vecteurs encodés, afin d’évaluer la performance sur les sous-ensembles train et test.

## Liens utiles

- [IMDB dataset sur Huggingface](https://huggingface.co/datasets/stanfordnlp/imdb)
- [GloVe embeddings](https://nlp.stanford.edu/projects/glove/)
- [scikit-learn - LogisticRegression](https://scikit-learn.org/1.5/modules/generated/sklearn.linear_model.LogisticRegression.html)
- [scikit-learn - MLPClassifier](https://scikit-learn.org/1.5/modules/generated/sklearn.neural_network.MLPClassifier.html#sklearn.neural_network.MLPClassifier)

