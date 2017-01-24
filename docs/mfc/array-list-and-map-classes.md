---
title: "Classes de tableaux, listes et mappages | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tableaux (C++), classes"
  - "classes de collection, listes"
  - "classes de collection, mappages"
  - "classes de liste"
  - "map (classes)"
ms.assetid: 81a13a7f-0c2c-4efd-b6bb-b4e624a0743d
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de tableaux, listes et mappages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour gérer des agrégats de données, la bibliothèque de classes fournit un groupe de classes de collection \(tables, listes, et cartes\) pouvant contenir différents types d'objets et types prédéfinis.  Les collections sont dynamiquement ordonnées.  Ces classes peuvent être utilisées dans tout programme, écrits pour Windows ou non.  Toutefois, elles sont les plus utiles pour implémenter les structures de données qui définissent les classes du document dans le framework d'application.  Vous pouvez facilement dériver les classes de collection spécialisées de ces éléments, ou vous pouvez les créer en fonction des classes du modèle.  Pour plus d'informations sur ces méthodes, consultez l'article [Collections](../mfc/collections.md).  Pour une liste de classes de collection de modèle, consultez l'article [Classes du modèle pour les tables, les listes, et la carte](../mfc/template-classes-for-arrays-lists-and-maps.md).  
  
 Les tables sont des structures de données unidimensionnelles stockées contiguement en mémoire.  Ils prennent en charge l'accès aléatoire très rapide \(RAM\) puisque l'adresse mémoire d'un élément donné peut être calculée en multipliant l'index de l'élément par la taille d'un élément et en ajoutant le résultat à l'adresse du tableau.  Les tableaux sont très coûteux si vous devez insérer des éléments dans le tableau, puisque le tableau entier après l'élément inséré doit être déplacé pour libérer de l'espace pour l'élément à insérer.  Les tableaux peuvent être développés et réduits selon les besoins.  
  
 Les listes sont similaires aux tableaux mais elles sont stockées différemment.  Chaque élément dans une liste inclut également un pointeur vers les éléments précédent et suivant, ce qui en fait une liste doublement liée.  Il est très rapide d'ajouter ou supprimer des éléments car cela implique seulement de modifier des pointeurs.  Toutefois, la liste peut être coûteuse puisque les recherches doivent commencer à un à la fin de la liste.  
  
 Les maps lient une valeur clé à une valeur de données.  Par exemple, la clé d'une map peut être une chaîne et la donnée un pointeur vers une liste.  Vous demanderiez à la carte de vous donner le pointeur associé à une chaîne spécifique.  Les recherches de map sont rapide car les maps utilisent des tables de hachage pour les recherches de clés.  Ajouter et supprimer des éléments est aussi rapide.  La carte est souvent utilisée avec d'autres structures de données en tant qu'index auxiliaire.  MFC utilise un type spécial de map appelé [map des messages](../mfc/mapping-messages.md) pour mapper des messages Windows à un pointeur à la fonction de handler du message.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)