# Stratégies quantitatives d’investissement

Concevoir et comparer deux stratégies systématiques sur les actions de l’Euro Stoxx 50 : suivi de tendance par moyennes mobiles et optimisation de portefeuille de Markowitz.

## Objectif

Le projet transforme des historiques de prix en décisions d’investissement reproductibles, puis compare les performances obtenues à l’indice Euro Stoxx 50.

Deux approches sont étudiées :

- une stratégie de tendance fondée sur les moyennes mobiles 50 et 200 jours ;
- une allocation rendement-risque fondée sur l’optimisation de Markowitz.

## Données

- cours historiques quotidiens des actions de l’Euro Stoxx 50 ;
- historique du SX5E comme benchmark ;
- Euribor 6 mois comme approximation du taux sans risque ;
- période principale de backtest : 2019-2022 ;
- analyse complémentaire : 2023.

Le pipeline inclut le nettoyage des formats, l’alignement temporel, le calcul des rendements et la séparation entre période d’estimation et période d’évaluation.

## Méthodologie

### Stratégie moyennes mobiles

- calcul des moyennes mobiles 50 et 200 jours ;
- position investie lorsque `MM50 > MM200` ;
- allocation équipondérée entre les actions sélectionnées ;
- placement au taux sans risque lorsqu’aucun actif n’est retenu.

### Portefeuille de Markowitz

- estimation des rendements moyens et de la matrice de covariance ;
- simulation de 10 000 portefeuilles long-only ;
- calcul du rendement, de la volatilité et du ratio de Sharpe ;
- sélection du portefeuille au ratio de Sharpe maximal.

## Résultats clés

La stratégie de moyennes mobiles sous-performe initialement autour du choc de 2020, puis dépasse le benchmark à partir d’environ mai 2020 et conserve globalement son avantage jusqu’à la fin du backtest.

Dans l’analyse 2023, le portefeuille de Markowitz atteint environ **18 % de rendement cumulé**, contre **17,5 %** pour le SX5E.

## Technologies

`Python` · `pandas` · `NumPy` · `Matplotlib` · séries temporelles · backtesting · optimisation de portefeuille

## Ce que ce projet démontre

- construction d’un pipeline financier complet ;
- création de signaux d’investissement ;
- comparaison à un benchmark ;
- analyse du compromis rendement-risque ;
- capacité à identifier les biais méthodologiques.

## Limites et améliorations

La version actuelle n’intègre pas les coûts de transaction, le slippage ni les dividendes. L’optimisation de Markowitz doit également être évaluée en walk-forward afin d’éviter tout biais rétrospectif.

## Auteurs

Projet académique réalisé par **Benjamin BAILLET** et **Yannick DJEIGO**.

---
