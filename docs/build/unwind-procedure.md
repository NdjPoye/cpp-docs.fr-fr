---
title: "Proc&#233;dure de d&#233;roulement | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 82c5d0ca-70be-4d1a-a306-bfe01c29159f
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Proc&#233;dure de d&#233;roulement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le tableau des codes de déroulement est trié dans l'ordre décroissant.  Lorsqu'une exception se produit, le contexte complet est stocké par le système d'exploitation dans un enregistrement de contexte.  Ensuite, la logique de distribution des exceptions est appelée afin d'exécuter à plusieurs reprises les étapes suivantes pour rechercher un gestionnaire d'exceptions.  
  
1.  Utilisez le RIP actuel stocké dans l'enregistrement de contexte pour rechercher une entrée de la table RUNTIME\_FUNCTION qui décrit la fonction en cours \(ou la partie de la fonction, en cas d'entrées UNWIND\_INFO chaînées\).  
  
2.  Si aucune entrée de table de fonctions n'est détectée, elle se trouve dans une fonction feuille, et RSP adresse directement le pointeur de retour.  Le pointeur de retour situé au niveau de \[RSP\] est stocké dans le contexte mis à jour, le RSP simulé est incrémenté de 8 et l'étape 1 est répétée.  
  
3.  Si une entrée de table de fonctions est recherchée, le RIP peut se trouver dans trois régions a\) dans un épilogue, b\) dans le prologue ou c\) dans le code qui peut être couvert par un gestionnaire d'exceptions.  
  
    -   Cas a\) Si le RIP est dans un épilogue, le contrôle quitte la fonction, aucun gestionnaire d'exceptions ne peut être associé à cette exception pour cette fonction et les effets de l'épilogue doivent être poursuivis pour calculer le contexte de la fonction appelante.  Pour déterminer si le RIP se trouve dans un épilogue, le flux de code du RIP est examiné.  Si ce flux de code peut être mis en correspondance avec la partie finale d'un épilogue légitime, alors il se trouve dans un épilogue et la partie restante de l'épilogue est simulée, l'enregistrement de contexte étant mis à jour à mesure que chaque instruction est traitée.  Ensuite, l'étape 1 est répétée.  
  
    -   Cas b\) Si le RIP se trouve dans le prologue, le contrôle n'a pas accédé à la fonction, aucun gestionnaire d'exceptions ne peut être associé à cette exception pour cette fonction et les effets du prologue doivent être annulés pour calculer le contexte de la fonction appelante.  Le RIP se trouve dans le prologue si la distance qui sépare le début de la fonction du RIP est inférieure ou égale à la taille du prologue encodée dans les informations de déroulement.  Les effets du prologue sont déroulés en recherchant, dans le tableau de codes de déroulement, la première entrée possédant un offset inférieur ou égal à l'offset du RIP à partir du début de la fonction et en annulant ensuite l'effet de tous les éléments restants dans le tableau des codes de déroulement.  L'étape 1 est répétée.  
  
    -   Cas c\) Si le RIP ne se trouve pas dans un prologue ou un épilogue et si la fonction possède un gestionnaire d'exceptions \(UNW\_FLAG\_EHANDLER est défini\), le gestionnaire spécifique au langage est appelé.  Il analyse ses données et appelle des fonctions de filtre le cas échéant.  Le gestionnaire spécifique au langage peut retourner que l'exception a été gérée ou que la recherche doit se poursuivre.  Il peut également initialiser directement un déroulement.  
  
4.  Si le gestionnaire spécifique au langage retourne un état géré, l'exécution se poursuit à l'aide de l'enregistrement de contexte d'origine.  
  
5.  S'il n'existe aucun gestionnaire spécifique au langage ou si le gestionnaire retourne un état « continuer la recherche », l'enregistrement de contexte doit être déroulé à l'état de l'appelant.  Cela s'effectue en traitant tous les éléments du tableau des codes de déroulement et annulant l'effet de chacun.  L'étape 1 est répétée.  
  
 Si des informations de déroulement chaînées sont impliquées, ces étapes de base sont quand même exécutées.  La seule différence réside dans le fait que lorsque la fin du tableau est atteinte, lors du parcours du tableau de codes de déroulement en vue de dérouler les effets d'un prologue, elles sont liées aux informations de déroulement parentes et l'intégralité du tableau des codes de déroulement détecté à cet endroit est parcourue.  Cette liaison se poursuit jusqu'à ce qu'elle atteigne des informations de déroulement sans l'indicateur UNW\_CHAINED\_INFO et qu'elle ait terminé de parcourir son tableau des codes de déroulement.  
  
 Le plus petit jeu de données de déroulement a une taille de 8 octets.  Cela pourrait représenter une fonction qui n'a alloué que 128 octets de pile maximum, et a éventuellement enregistré un registre non volatil.  Il s'agit étalement de la taille de la structure des informations de déroulement chaînées pour un prologue de longueur nulle sans code de déroulement.  
  
## Voir aussi  
 [Gestion des exceptions \(x64\)](../build/exception-handling-x64.md)