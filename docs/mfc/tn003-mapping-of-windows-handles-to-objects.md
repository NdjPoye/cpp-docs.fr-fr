---
title: "TN003&#160;: mappage des handles Windows &#224; des objets | Microsoft Docs"
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
  - "vc.mapping"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tables de handles"
  - "mappages, handles Windows à des objets"
  - "TN003"
  - "handles Windows d'objets (C++)"
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN003&#160;: mappage des handles Windows &#224; des objets
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette remarque décrit les routines de MFC qui prennent en charge les handles d'objet Windows de mappage des objets C\+\+.  
  
## Le problème  
 Les objets Windows sont généralement représentés par des objets [HANDLE](http://msdn.microsoft.com/library/windows/desktop/aa383751). Les classes MFC encapsulent les poignées Windows avec des objets MFC.  Les fonctions d'habillage de descripteur de la bibliothèque de classes de MFC vous permettent de trouver l'objet C\+\+ qui encapsule les fenêtres objet qui est un descripteur spécifique.  Toutefois, il arrive parfois qu'un objet n'ait pas d'objet de wrapper du actuel C\+\+ et le système crée alors un objet temporaire pour servir de wrapper C\+\+.  
  
 Les fenêtres objets qui utilisent les cartes de handle sont les suivantes :  
  
-   HWND \(classes dérivées de [CWnd](../mfc/reference/cwnd-class.md) et `CWnd`\)  
  
-   HDC \(classes dérivées de [CDC](../mfc/reference/cdc-class.md) et `CDC`\)  
  
-   HMENU \([CMenu](../mfc/reference/cmenu-class.md)\)  
  
-   HPEN \([CGdiObject](../mfc/reference/cgdiobject-class.md)\)  
  
-   HBRUSH \(`CGdiObject`\)  
  
-   HFONT \(`CGdiObject`\)  
  
-   HBITMAP \(`CGdiObject`\)  
  
-   HPALETTE \(`CGdiObject`\)  
  
-   HRGN \(`CGdiObject`\)  
  
-   HIMAGELIST \([CImageList](../mfc/reference/cimagelist-class.md)\)  
  
-   SOCKET \([CSocket](../mfc/reference/csocket-class.md)\)  
  
 Ayant un handle pour l'un de ces objets, vous pouvez trouver l'objet de MFC qui encapsule le handle en appelant la méthode statique `FromHandle`.  Par exemple, étant donné une HWND appelée `hWnd`, la ligne suivante retourne un pointeur vers `CWnd` qui encapsule `hWnd`:  
  
```  
CWnd::FromHandle(hWnd)  
```  
  
 Si `hWnd` n'est pas un objet spécifique de wrapper, un `CWnd` temporaire est créé pour encapsuler `hWnd`.  Cela permet d'obtenir un objet valide C\+\+ à partir de tout descripteur.  
  
 Après avoir un objet de wrapper, vous pouvez récupérer son handle depuis une variable membre publique de la classe wrapper.  Dans le cas d'un `CWnd`, `m_hWnd` contient le HWND pour cet objet.  
  
## Joindre des handles à des objets de MFC  
 Etant donné un objet créé récemment de wrapper de handle et un handle vers un objet Windows, vous pouvez associer les deux en appelant la fonction `Attach` comme dans l'exemple suivant :  
  
```  
CWnd myWnd;  
myWnd.Attach(hWnd);  
```  
  
 Cela donne une entrée dans la table permanente associant `myWnd` et `hWnd`.  L'appel à `CWnd::FromHandle(hWnd)` retourne maintenant un pointeur vers `myWnd`.  Lorsque `myWnd` est supprimé, le destructeur détruira automatiquement `hWnd` en appelant la fonction [DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682) Windows.  Si cela n'est pas souhaité, `hWnd` doit être détachée de `myWnd` avant que `myWnd` soit détruit \(normalement en laissant l'étendue à laquelle `myWnd` a été défini\).  La méthode `Detach` se présente comme suit :  
  
```  
myWnd.Detach();  
```  
  
## Plus sur les objets temporaires  
 Les objets temporaires sont créés chaque fois que `FromHandle` reçoit un handle qui n'a pas déjà d'objet wrapper.  Ces objets temporaires sont détachés de leur descripteur et supprimés par la fonction `DeleteTempMap`.  Par défaut [CWinThread::OnIdle](../Topic/CWinThread::OnIdle.md) appelle automatiquement `DeleteTempMap` pour chaque classe qui prend en charge les mappages temporaires du descripteur.  Cela signifie que vous ne pouvez pas supposer qu'un pointeur vers un objet temporaire est valide après le point de sortie de la fonction où le pointeur a été obtenu.  
  
## Objets wrapper et threads multiples  
 Les objets temporaires et permanents sont placés sur une base par thread.  Autrement dit, un thread ne peut pas accéder aux objets de wrapper C\+\+ d'un autre thread, qu'il soit temporaire ou permanent.  
  
 Pour passer les objets d'un thread à un autre, envoyez\-les toujours avec leur type natif `HANDLE`.  Passer un objet de wrapper C\+\+ d'un thread à un autre entraîne souvent des résultats inattendus.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)