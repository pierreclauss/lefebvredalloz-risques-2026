Atelier Risque de Crédit
================
Pierre Clauss
Mars 2026

**Objectif** : déterminer une CreditVaR à 1 an pour un portefeuille
constitué de 2 créances détenues par 2 entreprises, ici BNP Paribas et
Société Générale. Nous avons besoin pour cela de données sur les 4
paramètres de risque de crédit que sont l’EAD, la PD, la LGD et la
corrélation entre créances.

**L’Exposition Au Défaut** (EAD) est la même pour chaque créance, égale
à 1000.

Les **Probabilités de Défaut** (PD) sont extraites à partir des primes
![s](https://latex.codecogs.com/png.latex?s "s") de CDS de maturité
![T](https://latex.codecogs.com/png.latex?T "T") 1 an de chacune des 2
créances. Ces PD, qu’on appelle implicites, sont déterminées à partir du
*triangle du crédit* explicité ci-dessous et en supposant que le CDS a
été évalué avec un taux de recouvrement
![\delta=40\\](https://latex.codecogs.com/png.latex?%5Cdelta%3D40%5C%25 "\delta=40\%").

![PD=1-\exp\left(-\frac{s}{1-\delta}T\right)](https://latex.codecogs.com/png.latex?PD%3D1-%5Cexp%5Cleft%28-%5Cfrac%7Bs%7D%7B1-%5Cdelta%7DT%5Cright%29 "PD=1-\exp\left(-\frac{s}{1-\delta}T\right)")

La **Probabilité de Défaut** (PD) à 1 an est plus faible pour la créance
1, ce qui signifie que l’entreprise qui détient la créance 1 a un risque
qu’elle fasse défaut au cours de l’année moins important que celle qui
détient la créance 2.

Pour les **Loss Given Default** (LGD) moyennes, nous utilisons les
créances qui ont fait défaut dans le passé, qui ont les mêmes
caractéristiques de prêt et dont le prêteur évolue dans le même secteur
et le même pays. Ainsi, la créance 1 présente un meilleur taux de
recouvrement si jamais l’entreprise fait défaut (mobilisation de
créances ou crédit d’investissement par exemple) relativement à la
créance 2 (découvert ou prêt subordonné par exemple).

Enfin, pour déterminer la **corrélation** entre créances, on utilise
souvent les rentabilités des actions comme proxy du risque économique
des entreprises.

La **CreditVaR** pour le portefeuille constitué des 2 créances, de
niveau de confiance 99.9%, issue de *l’Asymptotic Single Risk Factor*
(ASRF) utilisé dans le cadre du calcul des fonds propres du comité de
Bâle, est formulé de la manière suivante, avec
![\Phi](https://latex.codecogs.com/png.latex?%5CPhi "\Phi") la fonction
de répartition de la loi Normale standard :

![CreditVaR = \sum\_{i=1}^2EAD_i\*LGD_i\*\Phi\left(\frac{\Phi^{-1}(PD_i)-\sqrt{\rho}\Phi^{-1}(1-99.9\\)}{\sqrt{1-\rho}}\right)](https://latex.codecogs.com/png.latex?CreditVaR%20%3D%20%5Csum_%7Bi%3D1%7D%5E2EAD_i%2ALGD_i%2A%5CPhi%5Cleft%28%5Cfrac%7B%5CPhi%5E%7B-1%7D%28PD_i%29-%5Csqrt%7B%5Crho%7D%5CPhi%5E%7B-1%7D%281-99.9%5C%25%29%7D%7B%5Csqrt%7B1-%5Crho%7D%7D%5Cright%29 "CreditVaR = \sum_{i=1}^2EAD_i*LGD_i*\Phi\left(\frac{\Phi^{-1}(PD_i)-\sqrt{\rho}\Phi^{-1}(1-99.9\%)}{\sqrt{1-\rho}}\right)")

La CreditVaR pour la créance 1 est logiquement plus faible que celle de
la créance 2 (PD et LGD moins importantes). La CreditVaR du portefeuille
des 2 créances est égal à 810, ce qui siginifie que la perte ne
dépassera 810 que dans 0.1% des cas.

Ce montant est bien entendu très important puisque le portefeuille n’est
pas diversifié avec seulement 2 créances.
