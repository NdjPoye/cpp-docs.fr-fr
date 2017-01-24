---
title: "Fonction de rappel pour CDC::SetAbortProc | Microsoft Docs"
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
  - "Callback Function for CDC::SetAbortProc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonctions de rappel, pour CDC::SetAbortProc"
ms.assetid: daa36d5d-15de-40fc-8d37-a865d06c4710
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonction de rappel pour CDC::SetAbortProc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le nom *AbortFunc* est un espace réservé pour le nom de la fonction par l'application fournie.  
  
## Syntaxe  
  
```  
  
      BOOL CALLBACK EXPORT AbortFunc(   
   HDC hPr,   
   int code    
);  
```  
  
#### Paramètres  
 *hPr*  
 Identifie le contexte de périphérique.  
  
 `code`  
 Spécifie si une erreur s'est produite.  Elle est 0 si aucune erreur ne s'est produite.  Il s'agit de **SP\_OUTOFDISK** si le Gestionnaire d'impression est actuellement hors de l'espace disque et davantage d'espace disque devient disponible si l'application est en attente.  Si `code` est **SP\_OUTOFDISK**, l'application n'est pas obligée d'interrompre le travail d'impression.  Dans le cas contraire, elle doit se référer au Gestionnaire d'impression en appelant les fonctions Windows **PeekMessage** ou **GetMessage**.  
  
## Valeur de retour  
 La valeur de retour de la fonction d'arrêt de gestionnaire est différente de zéro si le travail d'impression doit continuer, et 0 si il est annulé.  
  
## Notes  
 Le nom réel doit être exporté comme décrit dans la section remarques de [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md).  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md)