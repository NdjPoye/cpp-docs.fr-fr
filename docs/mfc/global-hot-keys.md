---
title: "Touches d’accès rapide globales | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 82297507d8725e6292def759272f48d0d63e84b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="global-hot-keys"></a>Touches globales d'accès rapide
Une touche d’accès rapide est associée à une fenêtre non-enfant particulière. Il permet à l’utilisateur Activer la fenêtre à partir de n’importe quelle partie du système. Une application définit une touche d’accès rapide pour une fenêtre particulière en envoyant le [message WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) message à cette fenêtre. Par exemple, si `m_HotKeyCtrl` est la [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) objet et `pMainWnd` est un pointeur vers la fenêtre à activer lorsque la touche d’accès rapide est activée, vous pouvez utiliser le code suivant pour associer la touche d’accès rapide spécifiée dans le contrôle avec la fenêtre vers laquelle pointe `pMainWnd`.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]  
  
 Chaque fois que l’utilisateur appuie sur une touche d’accès rapide, la fenêtre spécifiée reçoit un [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360) message spécifie **SC_HOTKEY** en tant que le type de la commande. Ce message Active également la fenêtre qui le reçoit. Étant donné que ce message n’inclut pas toutes les informations sur la clé exacte qui a été activée, l’à l’aide de cette méthode ne permet pas faire la distinction entre différentes touches d’accès rapide qui peuvent être jointe à la même fenêtre. Le raccourci clavier reste valid jusqu'à ce que l’application qui a envoyé **message WM_SETHOTKEY** se termine.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

