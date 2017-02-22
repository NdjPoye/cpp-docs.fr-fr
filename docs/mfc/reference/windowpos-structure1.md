---
title: "WINDOWPOS Structure1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WINDOWPOS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WINDOWPOS (structure)"
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# WINDOWPOS, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure de `WINDOWPOS` contient des informations sur la taille et l'emplacement d'un point.  
  
## Syntaxe  
  
```  
  
      typedef struct tagWINDOWPOS { /* wp */  
   HWND hwnd;  
   HWND hwndInsertAfter;  
   int x;  
   int y;  
   int cx;  
   int cy;  
   UINT flags;  
} WINDOWPOS;  
```  
  
#### Paramètres  
 *hwnd*  
 Identifie la fenêtre.  
  
 *hwndInsererApres*  
 Identifie la fenêtre par rapport à laquelle cette fenêtre est placée.  
  
 *x*  
 Spécifie la position du bord gauche de la fenêtre.  
  
 *y*  
 Spécifie la position du bord droit de la fenêtre.  
  
 `cx`  
 Spécifie la largeur de fenêtre en pixels de périphérique.  
  
 `cy`  
 Spécifie la hauteur de la fenêtre en pixels.  
  
 `flags`  
 Spécifie la fenêtre\- positionnement des options.  Ce membre peut avoir l'une des valeurs suivantes :  
  
-   **SWP\_DESSINERCADRE** Dessine un cadre \(défini dans la description de la classe de la fenêtre\) autour de la fenêtre.  La fenêtre reçoit un message de `WM_NCCALCSIZE`.  
  
-   **SWP\_FRAMECHANGED** envoie un message de `WM_NCCALCSIZE` dans la fenêtre, même si la taille de la fenêtre n'est pas modifiée.  Si cette valeur n'est spécifiée, `WM_NCCALCSIZE` est envoyé uniquement lorsque la taille de la fenêtre est modifiée.  
  
-   **SWP\_MASQUERFENETRE** masque la fenêtre.  
  
-   `SWP_NOACTIVATE` N'active pas la fenêtre.  
  
-   **SWP\_PASDECOPIEDESBITS** ignore le contenu entier de la zone client.  Si cet indicateur n'est pas spécifiée, le contenu valide de la zone client est stocké et copié dans la zone client après que la fenêtre soit triée ou replacée.  
  
-   `SWP_NOMOVE` conserve la position actuelle \(ignore les membres de **x** et de **y** \).  
  
-   **SWP\_NOOWNERZORDER** ne modifie pas la position de la fenêtre propriétaire dans l'ordre de plan.  
  
-   `SWP_NOSIZE` conserve la taille actuelle \(ignore les membres de **cx** et de **cy** \).  
  
-   **SWP\_PASDERAFRAICHISSEMENT** ne rafraîchit pas les modifications.  
  
-   **SWP\_NOREPOSITION** mêmes que **SWP\_NOOWNERZORDER**.  
  
-   **SWP\_NOSENDCHANGING** empêche la fenêtre de recevoir le message de `WM_WINDOWPOSCHANGING`.  
  
-   `SWP_NOZORDER` conserve le classement en cours \(ignore le membre de **hwndInsererApres** \).  
  
-   Affiche la fenêtre **SWP\_MONTRERFENETRE**.  
  
## Configuration requise  
 **En\-tête :** winuser.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md)