---
title: "Fonction de rappel pour CDC::GrayString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Callback Function for CDC::GrayString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonctions de rappel, for CDC::GrayString"
ms.assetid: 5217e183-df48-426b-931b-6245022ca36f
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Fonction de rappel pour CDC::GrayString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

*OutputFunc* est un espace réservé pour le nom de la fonction de rappel fournie par l'application.  
  
## Syntaxe  
  
```  
  
      BOOL CALLBACK EXPORT OutputFunc(   
   HDC hDC,   
   LPARAM lpData,   
   int nCount    
);  
```  
  
#### Paramètres  
 `hDC`  
 Identifie un contexte de périphérique mémoire avec une bitmap avec une largeur et une hauteur minimales spécifiées par `nWidth` et `nHeight` à `GrayString`.  
  
 `lpData`  
 Pointe la chaîne de caractères à ajouter.  
  
 `nCount`  
 Spécifie le nombre de caractères à obtenir.  
  
## Valeur de retour  
 La valeur renvoyée par la fonction de rappel doit être **TRUE** pour indiquer la réussite ; sinon ce doit être **FALSE**.  
  
## Notes  
 La fonction de rappel \(*OutputFunc*\) doit ajouter une image relativement aux coordonnées \(0,0\) plutôt que \(*x*, *y*\).  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GrayString](../Topic/CDC::GrayString.md)