---
title: Classe de CMFCDisableMenuAnimation | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
dev_langs:
- C++
helpviewer_keywords:
- CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 458a35e708db41ee393da70aedd653aca44cf802
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcdisablemenuanimation-class"></a>Classe de CMFCDisableMenuAnimation
Désactive l’animation de menu contextuel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCDisableMenuAnimation  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Construit un objet `CMFCDisableMenuAnimation`.|  
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCDisableMenuAnimation::Restore](#restore)|Restaure l’animation précédente que l’infrastructure utilisée pour afficher un menu contextuel.|  
  
### <a name="data-members"></a>Membres de données  
  
|||  
|-|-|  
|Name|Description|  
|`CMFCDisableMenuAnimation::m_animType`|Stocke le type d’animation de menu déroulant précédent.|  
  
### <a name="remarks"></a>Notes  
 Utilisez cette classe d’assistance pour désactiver temporairement l’animation de menu contextuel (par exemple, lorsque vous traitez la souris ou le clavier).  
  
 A `CMFCDisableMenuAnimation` objet désactive l’animation de menu contextuel pendant sa durée de vie. Le constructeur stocke le type d’animation de menu contextuel actuel dans le `m_animType` champ et comment l’animation actuelle type `CMFCPopupMenu::NO_ANIMATION`. Le destructeur restaure le type d’animation.  
  
 Vous pouvez créer un `CMFCDisableMenuAnimation` objet sur la pile pour désactiver l’animation de menu contextuel dans une fonction unique. Si vous souhaitez désactiver l’animation de menu contextuel entre les fonctions, créer un `CMFCDisableMenuAnimation` de l’objet sur le tas et supprimez-le lorsque vous souhaitez restaurer l’animation de menu contextuel.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser la pile pour désactiver temporairement d’animation de menu.  
  
 [!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxpopupmenu.h  
  
##  <a name="restore"></a>CMFCDisableMenuAnimation::Restore  
 Restaure l’animation précédente que l’infrastructure utilisée pour afficher un menu contextuel.  
  
```  
void Restore ();
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode est appelée par le `CMFCDisableMenuAnimation` destructeur pour restaurer l’animation précédente que l’infrastructure utilisée pour afficher un menu contextuel.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu, classe](../../mfc/reference/cmfcpopupmenu-class.md)
