---
title: "Introduction aux Classes de fenêtre ATL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- window classes
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 636fe8aa87b6880f5cda77fb46fc481d99d78a81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="introduction-to-atl-window-classes"></a>Introduction aux Classes de fenêtre ATL
Les classes ATL suivantes sont conçues pour implémenter et manipuler des fenêtres :  
  
-   [CWindow](../atl/reference/cwindow-class.md) permet de joindre un handle de fenêtre pour le `CWindow` objet. Vous appelez ensuite `CWindow` méthodes pour manipuler la fenêtre.  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md) vous permet d’implémenter une nouvelle fenêtre et de traiter les messages avec une table des messages. Vous pouvez créer une fenêtre basée sur un nouveau Windows, surclasser une classe existante ou d’une classe, une fenêtre existante.  
  
-   [CDialogImpl](../atl/reference/cdialogimpl-class.md) vous permet d’implémenter une modale ou une boîte de dialogue non modale et traiter les messages avec une table des messages.  
  
-   [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) est une classe prédéfinie qui implémente une fenêtre dont table des messages est contenue dans une autre classe. À l’aide de `CContainedWindowT` vous permet de centraliser le traitement des messages dans une classe.  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) vous permet d’implémenter une boîte de dialogue (modale ou non modale) qui héberge des contrôles ActiveX.  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) vous permet d’implémenter une boîte de dialogue modale avec les fonctionnalités de base.  
  
-   [Objet CAxWindow](../atl/reference/caxwindow-class.md) vous permet d’implémenter une fenêtre qui héberge un contrôle ActiveX.  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) vous permet d’implémenter une fenêtre qui héberge un contrôle ActiveX sous licence.  
  
 En plus des classes de fenêtre spécifique, ATL fournit plusieurs classes destinées à faciliter l’implémentation d’un objet fenêtre ATL. En voici la liste :  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) gère les informations d’une nouvelle classe de fenêtre.  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) et [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) fournissent une méthode simple de standardiser les traits d’un objet fenêtre ATL.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes de fenêtre](../atl/atl-window-classes.md)

