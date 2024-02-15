# Répartition des participants dans des bus
Solveur pour répartir les équipes dans les différents bus pour le départ au Week-End d'Intégration (WEI)

# Modèle Mathématique 

Ce modèle a pour but de permettre la répartition des équipes d'intégration dans les bus pour le départ vers le Week-end d'intégration. 

Aucune fonction objectif est utilisée, l'objectif est seulement de trouver une solution faisable

## Notation

Indices : i pour les bus {1-10}; j pour les équipes {1-38}\\

$K_i :$ capacité d'un bus <br>
$N_j :$ Nombre de personnes dans une équipe<br>
$C_j :$ Nombre de Chefs d'équipe dans une équipe<br>
$M_j :$ Nombre de mineurs dans une équipe<br>
$x_{ij} :$ 1 si équipe j dans le bus i, {0,1}<br>
$F_j :$ Faction d'une équipe, {-1,1}<br>
$P_i :$ Nombre de personnes ajoutées manuellement à un bus <br>

## Contraintes
Un seul bus par équipe : $\sum_{i=1}x_{ij} = 1, \forall j$ <br>
Ne pas dépasser la capacité d'un bus : 
    $\sum_{j=1} x_{ij}*N_j + P_i \leq K_i , \forall i$ <br>
2 équipes d'écart par faction par bus maximum :
   $-2 \leq \sum_{j=1}x_{ij}*F_j \leq 2 , \forall i$  <br>
Au maximum 10 mineurs par bus :
   $\sum_{j=1}x_{ij}*M_j \leq 10 , \forall i$  <br>
Au moins 6 Chef d'équipe par Bus : 
    $\sum_{j=1}x_{ij}*C_j \geq 6 , \forall i$ <br>

# Mise en page
Une macro VBA permet ensuite de prendre les résultats du solveur pour les mettre en forme afin d'en permettre l'export
    
