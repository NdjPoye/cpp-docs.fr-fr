---
title: "Fonction de rappel pour CDC::EnumObjects | Microsoft Docs"
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
  - "Callback Function for CDC::EnumObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonctions de rappel, pour CDC::EnumObjects"
ms.assetid: 380088b1-88a5-4fb4-bbb5-dd9e8386572b
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonction de rappel pour CDC::EnumObjects
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le nom *ObjectFunc* est un espace réservé pour le nom de la fonction fourni par l'application.  
  
## Syntaxe  
  
```  
  
      int CALLBACK EXPORT ObjectFunc(   
   LPSTR lpszLogObject,   
   LPSTR* lpData    
);  
```  
  
#### Paramètres  
 *lpszLogObject*  
 Pointe vers une structure de données [LOGPEN](../../mfc/reference/logpen-structure.md) ou [LOGBRUSH](../../mfc/reference/logbrush-structure.md) qui contient des informations sur les attributs logiques de l'objet.  
  
 `lpData`  
 Les points des données fournies par l'application sont transmis à la fonction `EnumObjects`.  
  
## Valeur de retour  
 La fonction de rappel retourne un `int`.  La valeur de ce retour est définie par l'utilisateur.  Si la fonction de rappel retourne 0, `EnumObjects` arrête l'énumération en avance.  
  
## Notes  
 Le nom réel doit être exporté.  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::EnumObjects](../Topic/CDC::EnumObjects.md)