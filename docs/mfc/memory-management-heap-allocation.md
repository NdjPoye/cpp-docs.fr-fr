---
title: "Gestion de la m&#233;moire&#160;: allocation de tas | Microsoft Docs"
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
helpviewer_keywords: 
  - "delete (opérateur), utiliser avec le débogage MFC"
  - "détection des fuites de mémoire"
  - "allocation des tas"
  - "allocation des tas, description"
  - "allocation de mémoire, mémoire de tas"
  - "fuites de mémoire, détecter"
  - "mémoire, détection des fuites"
  - "new (opérateur), utiliser avec le débogage MFC"
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Gestion de la m&#233;moire&#160;: allocation de tas
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le segment de mémoire est utilisé pour les besoins d'allocation de mémoire du programme.  Il s'agit d'une zone en dehors de programmation et de la pile.  Les programmes C standard utilisent les fonctions `malloc` et **free** pour allouer et libérer de la mémoire de segment.  La version de débogage de MFC fournit les versions de modifier des opérateurs prédéfinis **new** et **supprimer** C\+\+ pour allouer et de libérer des objets dans la mémoire du segment.  
  
 Lorsque vous utilisez **nouveau** et **supprimer** au lieu de `malloc` et de **libre**, vous pouvez bénéficier des améliorations en termes de débogage de la gestion de la mémoire de la bibliothèque de classes, qui peuvent être utiles lors de la détection des fuites de mémoire.  Lorsque vous créez votre programme avec la version Release de MFC, les versions standard des opérateurs de **nouveau** et de **supprimer** offrent un moyen efficace pour allouer et libérer de la mémoire \(la version préliminaire de MFC ne fournit pas les versions de modifier des opérateurs\).  
  
 Notez que la taille totale des objets alloués sur le segment est uniquement limitée par la mémoire virtuelle disponible sur votre système.  
  
## Voir aussi  
 [Gestion de la mémoire](../mfc/memory-management.md)