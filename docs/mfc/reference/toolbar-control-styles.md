---
title: "Styles de contrôle de barre d’outils | Documents Microsoft"
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
- ToolBar control styles
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
caps.latest.revision: 16
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
ms.openlocfilehash: 1c50009a50c5b80e007add9de679315df6aecea9
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="toolbar-control-styles"></a>Styles de contrôle ToolBar
[Classe de CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) a un jeu d’indicateurs de style qui déterminent l’apparence et le comportement du bouton. Vous pouvez définir une combinaison de ces indicateurs en appelant [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle). Cette rubrique répertorie les valeurs d’indicateur de style et leur signification.  
  
## <a name="property-values"></a>Valeurs de la propriété  
 Les valeurs suivantes déterminent le type de bouton qui représente le contrôle :  
  
 TBBS_BUTTON  
 Bouton de commande standard (par défaut).  
  
 TBBS_CHECKBOX  
 Case à cocher.  
  
 TBBS_CHECKGROUP  
 Le début d’un groupe de cases à cocher.  
  
 TBBS_GROUP  
 Le début d’un groupe de boutons.  
  
 TBBS_SEPARATOR  
 Séparateur.  
  
 Les valeurs suivantes représentent l’état actuel du contrôle :  
  
 TBBS_CHECKED  
 Case à cocher est activée.  
  
 TBBS_DISABLED  
 Le contrôle est désactivé.  
  
 TBBS_INDETERMINATE  
 Case à cocher est dans un état indéterminé.  
  
 TBBS_PRESSED  
 Bouton est enfoncé.  
  
 La valeur suivante modifie la disposition du bouton dans la barre d’outils :  
  
 TBBS_BREAK  
 Place l’élément sur une nouvelle ligne ou dans une nouvelle colonne sans séparation de colonnes.  
  
## <a name="remarks"></a>Notes  
 Le style actuel est stocké dans [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle). Ne définissez pas une nouvelle valeur dans `m_nStyle` directement, car certaines classes dérivées effectuent un traitement supplémentaire lorsque vous appelez `SetStyles`.  
  
 Le Gestionnaire visuel détermine l’apparence des boutons dans chaque état. Consultez la page [Gestionnaire de visualisation](../../mfc/visualization-manager.md) pour plus d’informations.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxtoolbarbutton.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMFCToolBarButton (classe)](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Gestionnaire de visualisation](../../mfc/visualization-manager.md)



