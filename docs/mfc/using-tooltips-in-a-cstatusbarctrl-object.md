---
title: "À l’aide des info-bulles dans un objet CStatusBarCtrl | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CStatusBarCtrl
dev_langs: C++
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf522d17d8abfc4b8dbf53baa24255ab23cfa621
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Utilisation d'info-bulles dans un objet CStatusBarCtrl
Pour activer les info-bulles pour un contrôle de barre d’état, vous devez créer le `CStatusBarCtrl` de l’objet avec la **SBT_TOOLTIPS** style.  
  
> [!NOTE]
>  Si vous utilisez un `CStatusBar` objet pour implémenter votre barre d’état, utilisez la `CStatusBar::CreateEx` (fonction). Permet de spécifier des styles supplémentaires pour le texte incorporé **CStatusBarCtrl** objet.  
  
 Une fois la `CStatusBarCtrl` objet n’a été créé, utilisez [CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) et [CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) pour définir et récupérer le texte d’info-bulle pour un volet spécifique.  
  
 Une fois l’info-bulle a été défini, il s’affiche uniquement si la partie possède une icône et aucun texte, ou si tout le texte ne peut pas être affichée à l’intérieur de la partie. Info-bulles ne sont pas pris en charge en mode simple.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

