---
title: "Conteneurs&#160;: &#233;tats d&#39;&#233;l&#233;ment client | Microsoft Docs"
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
  - "éléments clients et conteneurs OLE"
  - "durée de vie, états de durée de vie et conteneurs OLE (éléments clients)"
  - "conteneurs OLE, éléments clients (états)"
  - "états, conteneurs OLE (élément client)"
ms.assetid: e7021caa-bd07-4adb-976e-f5f3d025bc53
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Conteneurs&#160;: &#233;tats d&#39;&#233;l&#233;ment client
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique les différents états des tests d'un élément client dans sa durée de vie.  
  
 Un élément client transfère plusieurs conditions au moment de sa création, activé, modifié, et stocké.  Chaque fois que les modifications d'état de l'élément, l'infrastructure appelle [COleClientItem::OnChange](../Topic/COleClientItem::OnChange.md) avec notification d'`OLE_CHANGED_STATE`.  Le deuxième paramètre est une valeur de l'énumération de **COleClientItem::ItemState**.  Il peut avoir l'une des valeurs suivantes :  
  
-   **COleClientItem::emptyState**  
  
-   **COleClientItem::loadedState**  
  
-   **COleClientItem::openState**  
  
-   **COleClientItem::activeState**  
  
-   **COleClientItem::activeUIState**  
  
 Si l'état est vide, un élément client n'est pas encore entièrement un élément.  La mémoire a été allouée pour lui, mais elle n'a pas encore été initialisée avec les données OLE de l'élément.  Il s'agit de l'état d'un élément client est dans le moment où il a été créé par un appel à **new** mais n'a pas encore induite la deuxième étape de la création en deux étapes classique.  
  
 Dans la deuxième étape, effectué par un appel à un `COleClientItem::CreateFromFile` ou une fonction différente de **CreateFrom***xxxx*, l'élément est complètement créé.  Les données OLE \(un fichier ou d'une autre source, tels que le presse\-papiers\) a été associée à `COleClientItem`\- objet dérivé.  Maintenant l'élément est dans l'état chargé.  
  
 Lorsqu'un élément a été ouvert dans la fenêtre du serveur au lieu d'ouverture sur place dans le document de conteneur, il se trouve dans \(ou ouvrez entièrement\) l'état ouvert.  Dans cet état, une contre\-taille généralement est dessinée sur les performances de l'élément dans la fenêtre du conteneur pour indiquer que l'élément est plus active.  
  
 Lorsqu'un élément a été activé sur place, il passe, généralement que brièvement, via l'état actif.  Il passe à l'état actif de l'interface utilisateur, dans lequel le serveur a fusionné les menus, les barres d'outils, ainsi que d'autres composants de l'interface utilisateur avec celles du conteneur.  La présence de ces composants d'interface utilisateur fait l'état actif de l'interface utilisateur de l'état actif.  Sinon, l'état actif s'apparente à l'état actif de l'interface utilisateur.  Si la restauration est  supportée, le serveur est requis pour conserver les OLE des informations sur l'annulation de l'élément jusqu'à ce qu'il atteigne le chargement ou ouvrez l'état.  
  
## Voir aussi  
 [Conteneurs](../mfc/containers.md)   
 [Activation](../mfc/activation-cpp.md)   
 [Conteneurs : notifications d'élément client](../mfc/containers-client-item-notifications.md)   
 [Dispositifs de suivi](../mfc/trackers.md)   
 [CRectTracker Class](../mfc/reference/crecttracker-class.md)