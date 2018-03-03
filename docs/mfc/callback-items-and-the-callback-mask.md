---
title: "Éléments de rappel et masque de rappel | Documents Microsoft"
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
- callback items in CListCtrl class [MFC]
- CListCtrl class [MFC], callback item and callback mask
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24d9992b8a9db679b30624d85ede1a35bfd9826d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="callback-items-and-the-callback-mask"></a>Éléments de rappel et masque de rappel
Pour chacun de ses éléments, un contrôle list view stocke en général, le texte d’étiquette, l’index de liste d’images des icônes de l’élément, et un ensemble de bits indicateurs pour l’état de l’élément. Vous pouvez définir des éléments individuels en tant qu’éléments de rappel, qui sont utiles si votre application stocke déjà certaines des informations pour un élément.  
  
 Vous définissez un élément comme un élément de rappel en spécifiant les valeurs appropriées pour le `pszText` et `iImage` membres de la **LV_ITEM** structure (consultez [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem)). Si l’application gère le texte de l’élément ou de sous-élément, spécifiez la **LPSTR_TEXTCALLBACK** la valeur pour le `pszText` membre. Si l’application effectue le suivi de l’icône de l’élément, spécifiez la **I_IMAGECALLBACK** la valeur pour le `iImage` membre.  
  
 Outre la définition des éléments de rappel, vous pouvez également modifier le masque de rappel du contrôle. Ce masque est un ensemble de bits indicateurs qui spécifient les États des éléments pour lesquels l’application, plutôt que le contrôle, stocke les données actuelles. Le masque de rappel s’applique à tous les éléments du contrôle, contrairement à la désignation d’élément de rappel, qui s’applique à un élément spécifique. Le masque de rappel est zéro par défaut, c'est-à-dire que le contrôle effectue le suivi de tous les États d’élément. Pour modifier ce comportement par défaut, initialisez le masque à n’importe quelle combinaison des valeurs suivantes :  
  
-   `LVIS_CUT`L’élément est marqué pour une opération de couper-coller.  
  
-   `LVIS_DROPHILITED`L’élément est mis en surbrillance comme cible de glisser-déplacer.  
  
-   `LVIS_FOCUSED`L’élément a le focus.  
  
-   `LVIS_SELECTED`L’élément est sélectionné.  
  
-   **LVIS_OVERLAYMASK** l’application stocke l’index de l’image de superposition actuel pour chaque élément de liste d’images.  
  
-   **LVIS_STATEIMAGEMASK** l’application stocke l’index de liste d’images de l’image d’état actuel pour chaque élément.  
  
 Pour plus d’informations sur la récupération et la définition de ce masque, consultez [CListCtrl::GetCallbackMask](../mfc/reference/clistctrl-class.md#getcallbackmask) et [CListCtrl::SetCallbackMask](../mfc/reference/clistctrl-class.md#setcallbackmask).  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

