---
title: "Styles de barre de défilement | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SBS_VERT
- SBS_SIZEBOXBOTTOMRIGHTALIGN
- SBS_LEFTALIGN
- SBS_RIGHTALIGN
- SBS_TOPALIGN
- SBS_SIZEBOXTOPLEFTALIGN
- SBS_BOTTOMALIGN
- SBS_SIZEBOX
- SBS_HORZ
dev_langs:
- C++
helpviewer_keywords:
- SBS_HORZ constant
- SBS_TOPALIGN constant
- SBS_SIZEBOX constant
- SBS_BOTTOMALIGN constant
- SBS_VERT constant
- SBS_LEFTALIGN constant
- SBS_SIZEBOXBOTTOMRIGHTALIGN constant
- scroll bars, styles
- SBS_SIZEBOXTOPLEFTALIGN constant
- SBS_RIGHTALIGN constant
ms.assetid: 8bcde35b-387d-49ae-bdd6-7cda9f5dae26
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 778fe7b0f6f6319884df4ed9c5ccbe8e34bd8d42
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="scroll-bar-styles"></a>Styles de barre de défilement
-   **SBS_BOTTOMALIGN** utilisé avec le **SBS_HORZ** style. Le bord inférieur de la barre de défilement est aligné sur le bord inférieur du rectangle spécifié dans le **créer** fonction membre. La barre de défilement a la hauteur par défaut pour les barres de défilement du système.  
  
-   **SBS_HORZ** désigne une barre de défilement horizontale. Si ni le **SBS_BOTTOMALIGN** ni **SBS_TOPALIGN** style est spécifié, la barre de défilement de la hauteur, la largeur et la position spécifiée le **créer** fonction membre.  
  
-   **SBS_LEFTALIGN** utilisé avec le **SBS_VERT** style. Le côté gauche de la barre de défilement est aligné avec le bord gauche du rectangle spécifié dans le **créer** fonction membre. La barre de défilement a la largeur par défaut pour les barres de défilement du système.  
  
-   **SBS_RIGHTALIGN** utilisé avec le **SBS_VERT** style. Le côté droit de la barre de défilement est aligné avec le bord droit du rectangle spécifié dans le **créer** fonction membre. La barre de défilement a la largeur par défaut pour les barres de défilement du système.  
  
-   **SBS_SIZEBOX** désigne une zone de taille. Si ni le **SBS_SIZEBOXBOTTOMRIGHTALIGN** ni **SBS_SIZEBOXTOPLEFTALIGN** style est spécifié, la zone Taille a la hauteur, la largeur et la position spécifiée le **créer** fonction membre.  
  
-   **SBS_SIZEBOXBOTTOMRIGHTALIGN** utilisé avec le **SBS_SIZEBOX** style. Le coin inférieur droit de la zone taille est aligné avec le coin inférieur droit du rectangle spécifié dans le **créer** fonction membre. La zone Taille a la taille par défaut pour les zones de taille du système.  
  
-   **SBS_SIZEBOXTOPLEFTALIGN** utilisé avec le **SBS_SIZEBOX** style. Le coin supérieur gauche de la zone taille est aligné avec le coin supérieur gauche du rectangle spécifié dans le **créer** fonction membre. La zone Taille a la taille par défaut pour les zones de taille du système.  
  
-   **SBS_SIZEGRIP** identique **SBS_SIZEBOX**, mais avec une bordure en relief.  
  
-   **SBS_TOPALIGN** utilisé avec le **SBS_HORZ** style. Le bord supérieur de la barre de défilement est aligné sur le bord supérieur du rectangle spécifié dans le **créer** fonction membre. La barre de défilement a la hauteur par défaut pour les barres de défilement du système.  
  
-   **SBS_VERT** désigne une barre de défilement verticale. Si ni le **SBS_RIGHTALIGN** ni **SBS_LEFTALIGN** style est spécifié, la barre de défilement de la hauteur, la largeur et la position spécifiée le **créer** fonction membre.  
  
## <a name="see-also"></a>Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CScrollBar::Create](../../mfc/reference/cscrollbar-class.md#create)   
 [Styles de contrôle de barre de défilement](http://msdn.microsoft.com/library/windows/desktop/bb787533)


