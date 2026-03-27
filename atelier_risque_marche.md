Atelier Risque de Marché
================
Pierre Clauss
Mars 2026

**Objectif** : Comparer la **volatilité** (annualisée) et la
**Value-at-Risk** (VaR) historique comme indicateurs de risque de marché
sur des indices actions et obligations.

**Données** : 3 indices actions CAC 40, NASDAQ 100 et MSCI Emerging
Markets sont étudiés entre 2003 et aujourd’hui pour prendre en compte
différentes bulles et crises (*subprimes*, crise souveraine, Covid,
inflation). Un indice obligataire est ajouté, le Bloomberg US Aggregate,
combinant obligations souveraines et *corporates* bien notées.

**Définition** : La VaR repose sur deux paramètres principaux, l’horizon
1 jour (qui correspond à la périodicité des rentabilités quotidiennes
des indices) et le niveau de probabilité 1% et 0.1% (ou niveau de
confiance 99% et 99.9%).

**Analyses des résultats** : Le CAC 40 est un indice actions qu’on peut
imaginer moins risqué que l’indice actions NASDAQ 100. Cette intuition
se vérifie sur l’ensemble de la période.

En revanche, lors de la crise souveraine en Europe, on observe que la
volatilité du CAC 40 est plus élevée que celle du NASDAQ 100. Il en est
de même pour la VaR 1% en valeur absolue plus faible pour l’indice
NASDAQ 100 sur cette période.

Ainsi, investir dans l’indice NASDAQ 100 peut induire un risque de
perte, survenant une fois tous les 100 jours (soit 2 à 3 fois par an),
de 3.75% alors que pour l’indice CAC 40, ce risque de perte augmente à
4.59%.

La VaR 0.1% permet au contraire de conclure que le risque de l’indice
NASDAQ 100 est plus important comme on pouvait l’anticiper : investir
dans l’indice NASDAQ 100 peut induire un risque de perte, survenant une
fois tous les 1000 jours (soit tous les 4 ans), de 5.81% alors que pour
l’indice CAC 40, ce risque de perte diminue à 5.46%.

**Conclusion** : La volatilité et la VaR 1% sont des indicateurs de
risque **moyen** et la VaR 0.1% est un indicateur de risque **extrême**.
