---
title: "MSG Structure1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSG (structure)"
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# MSG, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `MSG` Contient des informations sur les messages de la file d'attente de messages d'un thread.  
  
## Syntaxe  
  
```  
  
      typedef struct tagMSG {     // msg    
   HWND hwnd;  
   UINT message;  
   WPARAM wParam;  
   LPARAM lParam;  
   DWORD time;  
   POINT pt;  
} MSG;  
```  
  
#### Paramètres  
 *hwnd*  
 Identifie la fenêtre dont la procédure de fenêtre reçoit le message.  
  
 `message`  
 Spécifie le nombre de messages.  
  
 `wParam`  
 Spécifie les informations supplémentaires à propos du message.  La signification exacte dépend de la valeur du membre **message**.  
  
 `lParam`  
 Spécifie les informations supplémentaires à propos du message.  La signification exacte dépend de la valeur du membre **message**.  
  
 `time`  
 Spécifie l'heure à laquelle le message a été posté.  
  
 `pt`  
 Spécifie la position du curseur, en coordonnées d'écran, lorsque le message a été émis.  
  
## Configuration requise  
 **En\-tête :** winuser.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)