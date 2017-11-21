---
title: "À l’aide d’une fenêtre (ATL) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0e4cc64dd524615c003619466f66f4bf92ab62f7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="using-a-window"></a>À l’aide d’une fenêtre
Classe [CWindow](../atl/reference/cwindow-class.md) vous permet d’utiliser une fenêtre. Une fois que vous attachez une fenêtre à un `CWindow` de l’objet, vous pouvez ensuite appeler `CWindow` méthodes pour manipuler la fenêtre. `CWindow`contient également une `HWND` pour convertir un `CWindow` de l’objet à un `HWND`. Par conséquent, vous pouvez passer un `CWindow` objet à n’importe quelle fonction qui requiert un handle de fenêtre. Vous pouvez facilement combiner `CWindow` appels de méthode et les appels de fonction Win32, sans créer d’objets temporaires.  
  
 Étant donné que `CWindow` a un membre de données uniquement deux (un handle de fenêtre et les dimensions par défaut), il n’impose pas de surcharge sur votre code. En outre, la plupart de la `CWindow` encapsulent simplement les fonctions API Win32 correspondantes. À l’aide de `CWindow`, le `HWND` membres est automatiquement passée à la fonction Win32.  
  
 Outre l’utilisation de `CWindow` directement, vous pouvez également dériver pour ajouter des données ou du code à votre classe. ATL elle-même dérive les trois classes de `CWindow`: [CWindowImpl](../atl/implementing-a-window.md), [CDialogImpl](../atl/implementing-a-dialog-box.md), et [CContainedWindowT](../atl/using-contained-windows.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Classes de fenêtre](../atl/atl-window-classes.md)

