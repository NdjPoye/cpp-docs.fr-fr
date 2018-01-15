---
title: "Styles du contrôle Progress | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6186372dc3ac8bc1000a71706971c9ff72078c5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="styles-for-the-progress-control"></a>Styles du contrôle Progress
Lorsque vous créez initialement du contrôle progress ([CProgressCtrl::Create](../mfc/reference/cprogressctrl-class.md#create)), utilisez le `dwStyle` pour spécifier les styles de fenêtre souhaitée pour votre contrôle de progression. La liste suivante détaille les styles de fenêtre applicables. Le contrôle ignore tout style de fenêtre autres que ceux répertoriés ici. Vous devez toujours créer le contrôle comme une fenêtre enfant, généralement d’une boîte de dialogue parent.  
  
|Style de fenêtre|Effet|  
|------------------|------------|  
|`WS_BORDER`|Crée une bordure autour de la fenêtre.|  
|**WS_CHILD**|Crée une fenêtre enfant (doit toujours être utilisé pour `CProgressCtrl`).|  
|**WS_CLIPCHILDREN**|Exclut la zone occupée par les fenêtres enfants lorsque vous dessinez au sein de la fenêtre parente. Utilisé lorsque vous créez la fenêtre parente.|  
|**WS_CLIPSIBLINGS**|Fenêtres enfants de clips entre eux.|  
|**WS_DISABLED**|Crée une fenêtre qui est initialement désactivée.|  
|**WS_VISIBLE**|Crée une fenêtre est visible initialement.|  
|**WS_TABSTOP**|Spécifie que le contrôle peut recevoir le focus lorsque l’utilisateur appuie sur la touche TAB pour passer à ce dernier.|  
  
 En outre, vous pouvez spécifier deux styles qui s’appliquent uniquement au contrôle de progression, `PBS_VERTICAL` et `PBS_SMOOTH`.  
  
 Utilisez `PBS_VERTICAL` pour orienter le contrôle verticalement, plutôt qu’horizontalement. Utilisez `PBS_SMOOTH` pour remplir le contrôle complètement, au lieu d’afficher de petits carrés qui remplit le contrôle de façon incrémentielle.  
  
 Sans `PBS_SMOOTH` style :  
  
 ![Style de barre de progression standard](../mfc/media/vc4ruw1.gif "vc4ruw1")  
  
 Avec `PBS_SMOOTH` et `PBS_VERTICAL` styles :  
  
 ![Style, lisse et vertical de la barre de progression](../mfc/media/vc4ruw2.gif "vc4ruw2")  
  
 Pour plus d’informations, consultez [Styles de fenêtre](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc) dans les *référence MFC*.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CProgressCtrl](../mfc/using-cprogressctrl.md)

