---
title: "Relation entre un objet fenêtre C++ et HWND | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: HWND
dev_langs: C++
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b441077de3a81de569627b6d7acf7cee8ca17b33
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>Relation entre un objet fenêtre C++ et un HWND
La fenêtre *objet* est un objet de C++ `CWnd` classe (ou une classe dérivée) que votre programme crée directement. Il va et vient en réponse aux appels de constructeur et le destructeur de votre programme. Les fenêtres *fenêtre*, quant à lui, est un handle opaque vers une structure de données interne Windows qui correspond à une fenêtre et consomme des ressources système lorsqu’il est présent. Une fenêtre Windows est identifiée par un « handle de fenêtre » (`HWND`) et est créé après le `CWnd` objet est créé par un appel à la **créer** fonction membre de classe `CWnd`. La fenêtre peut être détruite par un appel de programme ou par l’action d’un utilisateur. Le handle de fenêtre est stocké dans l’objet de fenêtre `m_hWnd` variable membre. L’illustration suivante montre la relation entre l’objet fenêtre C++ et la fenêtre Windows. Création de fenêtres est décrite dans [création de fenêtres](../mfc/creating-windows.md). Détruire des fenêtres sont décrite dans [destruction d’objets](../mfc/destroying-window-objects.md).  
  
 ![CWnd objet fenêtre et fenêtre résultante](../mfc/media/vc37fj1.gif "vc37fj1")  
Objet fenêtre et fenêtre Windows  
  
## <a name="see-also"></a>Voir aussi  
 [Objets fenêtre](../mfc/window-objects.md)

