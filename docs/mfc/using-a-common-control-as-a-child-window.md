---
title: "À l’aide d’un contrôle commun en tant que fenêtre enfant | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 475c769bf09c0693c04780712b85884ae7c48862
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-common-control-as-a-child-window"></a>Utilisation d'un contrôle commun en tant que fenêtre enfant
Un des contrôles communs Windows peut servir en tant que fenêtre enfant de toute autre fenêtre. La procédure suivante décrit comment créer un contrôle commun de manière dynamique et travailler avec lui.  
  
### <a name="to-use-a-common-control-as-a-child-window"></a>Pour utiliser un contrôle commun en tant que fenêtre enfant  
  
1.  Définissez le contrôle dans la classe connexe ou du gestionnaire.  
  
2.  Utilisez la substitution de la [CWnd::Create](../mfc/reference/cwnd-class.md#create) méthode pour créer le contrôle Windows.  
  
3.  Une fois que le contrôle a été créé (en même temps que le `OnCreate` gestionnaire si sous-classe le contrôle), vous pouvez manipuler le contrôle à l’aide de ses fonctions membres. Consultez les descriptions des contrôles individuels à [contrôles](../mfc/controls-mfc.md) pour plus d’informations sur les méthodes.  
  
4.  Lorsque vous avez terminé avec le contrôle, utilisez [CWnd::DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) détruire le contrôle.  
  
## <a name="see-also"></a>Voir aussi  
 [Création et utilisation de contrôles](../mfc/making-and-using-controls.md)   
 [Contrôles](../mfc/controls-mfc.md)

