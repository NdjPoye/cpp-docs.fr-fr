---
title: "Using a Window | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, fenêtres"
  - "CWindow class, about CWindow class"
  - "windows [C++], ATL"
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Using a Window
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe [CWindow](../atl/reference/cwindow-class.md) vous permet d'utiliser une fenêtre.  Une fois que vous attachez une fenêtre à un objet d' `CWindow` , vous pouvez ensuite appeler des méthodes d' `CWindow` pour manipuler la fenêtre.  `CWindow` contient également un opérateur d' `HWND` pour convertir un objet d' `CWindow` à `HWND`.  Vous pouvez passer un objet d' `CWindow` à une fonction qui requiert un handle vers une fenêtre.  Vous pouvez facilement mélanger des appels d'appels de méthode d' `CWindow` et de fonction Win32, sans créer un objet temporaire.  
  
 Étant donné qu' `CWindow` a le membre que deux \(un handle de fenêtre et les dimensions de valeur par défaut\), elle n'applique pas une charge mémoire à votre code.  En outre, de nombreux l'API Win32 correspondant d'enveloppe de méthodes d' `CWindow` simplement s'exécute.  À l'aide de `CWindow`, le membre d' `HWND` est automatiquement passée à la fonction Win32.  
  
 En plus de utiliser `CWindow` directement, vous pouvez également dériver de lui ajouter des données ou du code à votre classe.  ATL lui\-même dérive trois classes d' `CWindow`: [CWindowImpl](../atl/implementing-a-window.md), [CDialogImpl](../atl/implementing-a-dialog-box.md), et [CContainedWindowT](../atl/using-contained-windows.md).  
  
## Voir aussi  
 [classes de fenêtre](../atl/atl-window-classes.md)