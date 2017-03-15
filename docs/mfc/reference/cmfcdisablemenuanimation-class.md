---
title: Classe de CMFCDisableMenuAnimation | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDisableMenuAnimation
dev_langs:
- C++
helpviewer_keywords:
- CMFCDisableMenuAnimation class
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
caps.latest.revision: 22
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ea0be944ca70d6f8317fd4bc60fdd50ecc714438
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdisablemenuanimation-class"></a>CMFCDisableMenuAnimation (classe)
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
|Nom|Description|  
|`CMFCDisableMenuAnimation::m_animType`|Stocke le type d’animation de menu contextuel précédente.|  
  
### <a name="remarks"></a>Notes  
 Cette classe d’assistance permet de désactiver temporairement d’animation de menu contextuel (par exemple, lorsque vous traitez la souris ou le clavier).  
  
 Un `CMFCDisableMenuAnimation` objet désactive l’animation de menu contextuel pendant sa durée de vie. Le constructeur stocke le type d’animation de menu contextuel actuel dans le `m_animType` champ et comment l’animation en cours de type `CMFCPopupMenu::NO_ANIMATION`. Le destructeur restaure le type d’animation.  
  
 Vous pouvez créer un `CMFCDisableMenuAnimation` objet sur la pile pour désactiver l’animation de menu contextuel dans une fonction unique. Si vous souhaitez désactiver l’animation de menu contextuel entre les fonctions, créer un `CMFCDisableMenuAnimation` de l’objet sur le tas, puis le supprimer lorsque vous souhaitez restaurer l’animation de menu contextuel.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser la pile pour désactiver temporairement d’animation de menu.  
  
 [!code-cpp[NVC_MFC_Misc n °&1;](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxpopupmenu.h  
  
##  <a name="a-namerestorea--cmfcdisablemenuanimationrestore"></a><a name="restore"></a>CMFCDisableMenuAnimation::Restore  
 Restaure l’animation précédente que l’infrastructure utilisée pour afficher un menu contextuel.  
  
```  
void Restore ();
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode est appelée par le `CMFCDisableMenuAnimation` destructeur pour restaurer l’animation précédente que l’infrastructure utilisée pour afficher un menu contextuel.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu (classe)](../../mfc/reference/cmfcpopupmenu-class.md)

