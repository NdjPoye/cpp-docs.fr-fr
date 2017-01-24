---
title: "CREATESTRUCT, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CREATESTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CREATESTRUCT (structure)"
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CREATESTRUCT, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `CREATESTRUCT` définit les paramètres d'initialisation transmis à la procédure d'affichage d'une application.  
  
## Syntaxe  
  
```  
  
      typedef struct tagCREATESTRUCT {  
   LPVOID lpCreateParams;  
   HANDLE hInstance;  
   HMENU hMenu;  
   HWND hwndParent;  
   int cy;  
   int cx;  
   int y;  
   int x;  
   LONG style;  
   LPCSTR lpszName;  
   LPCSTR lpszClass;  
   DWORD dwExStyle;  
} CREATESTRUCT;  
```  
  
#### Paramètres  
 `lpCreateParams`  
 Points de données à utiliser pour créer la fenêtre.  
  
 `hInstance`  
 Identifie le gestionnaire d'instance du module de celui qui possède la nouvelle fenêtre.  
  
 `hMenu`  
 Identifie le menu à utiliser dans une nouvelle fenêtre.  S'il s'agit d'une fenêtre enfant, contient l'ID de type entier.  
  
 `hwndParent`  
 Identifie la fenêtre propriétaire de la nouvelle fenêtre.  Ce membre est **NULL** si la nouvelle fenêtre est une fenêtre de niveau supérieur.  
  
 `cy`  
 Spécifie la hauteur de la nouvelle fenêtre.  
  
 `cx`  
 Spécifie la largeur de la nouvelle fenêtre.  
  
 `y`  
 Spécifie la coordonnée y de l'angle supérieur gauche de la nouvelle fenêtre.  Les coordonnées sont relatives à la fenêtre parente si une nouvelle fenêtre est une fenêtre enfant ; sinon les coordonnées sont relatives à l'origine de l'écran.  
  
 `x`  
 Spécifie la coordonnée x de l'angle supérieur gauche de la nouvelle fenêtre.  Les coordonnées sont relatives à la fenêtre parente si une nouvelle fenêtre est une fenêtre enfant ; sinon les coordonnées sont relatives à l'origine de l'écran.  
  
 `style`  
 Spécifie le [style](../../mfc/reference/styles-used-by-mfc.md) de la nouvelle fenêtre.  
  
 `lpszName`  
 Pointe vers la chaîne terminée par le caractère NULL qui spécifie le nom de la nouvelle fenêtre.  
  
 `lpszClass`  
 Pointe vers la chaîne terminée par le caractère NULL qui spécifie le nom de classe windows de la nouvelle fenêtre \(une structure [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) ; pour plus d'informations, consultez [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]\).  
  
 `dwExStyle`  
 Spécifie le [style étendue](../../mfc/reference/extended-window-styles.md) pour la nouvelle fenêtre.  
  
## Configuration requise  
 **En\-tête :** winuser.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../Topic/CWnd::OnCreate.md)