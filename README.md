# Analyse du comportement d'achat des clients

## Présentation du projet

Ce projet de data analytics étudie le comportement d'achat de clients d'une entreprise e-commerce. Son objectif est de répondre à la question suivante :

> Quels facteurs sont associés au comportement d'achat des clients et comment exploiter les résultats pour améliorer les ventes et la fidélisation ?

L'analyse repose sur deux indicateurs principaux :

- le montant d'achat ;
- la fréquence d'achat.

Les facteurs étudiés concernent les caractéristiques des clients, les produits et le contexte d'achat. Des indicateurs commerciaux ont également été construits afin d'évaluer les ventes et la fidélisation.

## Jeu de données

Le jeu de données contient **3 900 observations** et regroupe des informations sur :

- les clients : âge, genre, localisation, abonnement et historique d'achats ;
- les produits : article, catégorie, taille et couleur ;
- le contexte d'achat : saison, remise, mode de livraison et moyen de paiement ;
- le comportement client : montant d'achat, fréquence d'achat et note attribuée.

Deux variables ont été créées pour faciliter l'analyse :

- `Age_Group` : regroupement des clients par tranche d'âge ;
- `Purchase_Frequency_Num` : conversion des fréquences textuelles en fréquence annuelle approximative.

## Outils utilisés

- **Python** et **Pandas** : préparation, nettoyage et analyse exploratoire des données ;
- **tests statistiques** : test t de Welch, ANOVA et corrélations ;
- **Power BI** et **DAX** : création des indicateurs et du tableau de bord interactif ;
- **rapport d'analyse** : synthèse des résultats et recommandations commerciales.


## Étapes du projet

1. Importation et exploration du jeu de données avec Python.
2. Contrôle de la qualité des données.
3. Recherche des doublons, valeurs manquantes et valeurs aberrantes.
4. Suppression de la variable redondante `Promo Code Used`.
5. Création des variables `Age_Group` et `Purchase_Frequency_Num`.
6. Analyse exploratoire des facteurs liés aux clients, aux produits et au contexte d'achat.
7. Validation des différences observées à l'aide de tests statistiques.
8. Création des indicateurs commerciaux et du tableau de bord Power BI.
9. Interprétation des résultats et formulation de recommandations business.

## Préparation et qualité des données

- Aucun doublon complet n'a été détecté.
- Aucune valeur aberrante n'a été identifiée selon la règle de l'écart interquartile (IQR).
- Les **37 valeurs manquantes** de `Review Rating` ont été conservées comme telles afin d'éviter une imputation arbitraire.
- La variable `Promo Code Used` a été retirée de la version analytique, car elle était parfaitement redondante avec `Discount Applied`.

## Tableau de bord Power BI

Le tableau de bord permet d'explorer de manière interactive :

- le chiffre d'affaires ;
- le montant moyen des achats ;
- la fréquence d'achat ;
- le taux d'abonnement ;
- les performances par catégorie de produits ;
- les différences observées selon les caractéristiques des clients et le contexte d'achat.

## Principaux résultats

- Parmi les facteurs catégoriels testés, **seule la saison présente une association statistiquement significative avec le montant d'achat** au seuil de 5 % (`p = 0,0106`).
- Aucun facteur catégoriel testé ne présente d'association statistiquement significative avec la fréquence d'achat.
- Le nombre d'achats précédents présente des corrélations linéaires pratiquement nulles avec le montant et la fréquence d'achat.
- La catégorie **Clothing** génère le chiffre d'affaires le plus élevé, principalement grâce à un volume d'achats supérieur.
- Le taux d'abonnement observé est de **27 %**, mais aucune différence statistiquement significative du montant ou de la fréquence d'achat n'a été détectée selon le statut d'abonnement.

Ces résultats indiquent des **associations statistiques** et ne permettent pas d'établir des relations de cause à effet.

## Recommandations business

- Consolider les catégories qui contribuent le plus au chiffre d'affaires, notamment `Clothing`.
- Adapter prudemment le calendrier commercial, l'assortiment et les campagnes marketing à la saisonnalité observée.
- Renforcer le programme de fidélisation tout en mesurant son effet réel sur la rétention et la valeur client.
- Tester les futures actions commerciales, par exemple avec des tests A/B, avant de les généraliser.

## Comment exécuter le projet

1. Cloner ou télécharger le dépôt.
2. Installer Python ainsi que les bibliothèques indiquées dans le fichier de dépendances du projet.
3. Placer le jeu de données dans le dossier prévu à cet effet.
4. Ouvrir le notebook d'analyse dans Jupyter Notebook ou JupyterLab.
5. Exécuter les cellules dans l'ordre afin de reproduire la préparation, l'analyse exploratoire et les tests statistiques.
6. Ouvrir le fichier `.pbix` avec Power BI Desktop pour consulter le tableau de bord interactif.

## Conclusion

Ce projet montre comment transformer des données clients brutes en informations utiles à la décision. Il combine préparation des données, analyse exploratoire, validation statistique et visualisation interactive afin de proposer des recommandations commerciales mesurables et prudentes.
