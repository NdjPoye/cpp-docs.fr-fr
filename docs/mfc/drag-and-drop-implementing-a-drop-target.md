---
title: "Glisser-d&#233;placer&#160;: impl&#233;mentation d&#39;une cible de d&#233;placement | Microsoft Docs"
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
  - "glisser-déplacer, cible de déplacement"
  - "OLE (glisser-déplacer), cible de déplacement"
  - "OLE (glisser-déplacer), implémenter des cibles de déplacement"
ms.assetid: 0689f1ec-5326-4008-b226-4b373c881358
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Glisser-d&#233;placer&#160;: impl&#233;mentation d&#39;une cible de d&#233;placement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article comment faire de votre application une cible de suppression.  Implémenter une cible de suppression donne légèrement plus de travail que l'implémentation d'une source déroulante, mais elle est toujours relativement simple.  Ces techniques s'appliquent également à des applications non OLE.  
  
#### Pour implémenter une cible de suppression  
  
1.  Ajoutez une variable membre à chaque vue dans l'application que vous souhaitez être une cible de suppression.  Cette variable membre doit être de type `COleDropTarget` ou d'une classe dérivée de celle\-ci.  
  
2.  De la fonction de votre classe de vue qui traite le message `WM_CREATE` \(généralement `OnCreate`\), appelez la nouvelle fonction membre de la variable membre `Register`.  `Revoke` est appelé automatiquement pour vous lorsque la vue est détruite.  
  
3.  Remplacer les fonctions suivantes.  Si vous souhaitez le même comportement dans l'ensemble de votre application, remplacez ces fonctions dans la classe d'affichage.  Si vous souhaitez modifier le comportement dans les cas isolés ou peut\-être activer la suppression de fenêtre non\-`CView`, remplacez ces fonctions dans votre classe dérivée de `COleDropTarget`.  
  
    |Substitution|Pour laisser|  
    |------------------|------------------|  
    |`OnDragEnter`|Opérations de suppression se produire dans la fenêtre.  Appelé lorsque le curseur entre dans la fenêtre pour la première fois.|  
    |`OnDragLeave`|Comportement particulier lorsque l'opération de glisser\-déplacer quitte la fenêtre spécifiée.|  
    |`OnDragOver`|Supprimer les opérations se produisant dans la fenêtre.  Appelé lorsque le curseur est déplacé dans la fenêtre.|  
    |`OnDrop`|Gestion des données étant supprimées dans la fenêtre spécifiée.|  
    |`OnScrollBy`|Comportement particulier pour lorsque le défilement est nécessaire dans la fenêtre cible.|  
  
 Consultez le fichier de MAINVIEW.CPP qui fait partie de l'exemple de liaison et d'incorporation d'objets MFC [OCLIENT](../top/visual-cpp-samples.md) pour obtenir un exemple sur la façon dont elles fonctionnent ensemble.  
  
 Pour plus d'informations, consultez :  
  
-   [Implémenter une source de suppression](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [Création et Destruction d'Objets de données et de sources de données OLE](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Manipuler des Objets de données et Sources de données OLE](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## Voir aussi  
 [Glisser\-déplacer \(OLE\)](../mfc/drag-and-drop-ole.md)   
 [COleDropTarget Class](../mfc/reference/coledroptarget-class.md)