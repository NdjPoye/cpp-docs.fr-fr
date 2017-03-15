---
title: Classe CParabolicTransitionFromAcceleration | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CParabolicTransitionFromAcceleration
- CParabolicTransitionFromAcceleration
dev_langs:
- C++
helpviewer_keywords:
- CParabolicTransitionFromAcceleration class
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
caps.latest.revision: 18
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f0d3089a01cd244851be3d4bdf0453101a9c8274
ms.lasthandoff: 02/24/2017

---
# <a name="cparabolictransitionfromacceleration-class"></a>CParabolicTransitionFromAcceleration, classe
Encapsule une transition d'accélération parabolique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CParabolicTransitionFromAcceleration : public CBaseTransition;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration](#cparabolictransitionfromacceleration)|Construit une transition d’accélération parabolique et l’initialise avec les paramètres spécifiés.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::Create](#create)|Appelle la bibliothèque des transitions pour créer l’objet COM de transition encapsulé. (Substitue [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::m_dblAcceleration](#m_dblacceleration)|L’accélération de la variable d’animation pendant la transition.|  
|[CParabolicTransitionFromAcceleration::m_dblFinalValue](#m_dblfinalvalue)|La valeur de la variable d’animation à la fin de la transition.|  
|[CParabolicTransitionFromAcceleration::m_dblFinalVelocity](#m_dblfinalvelocity)|La rapidité de la variable d’animation à la fin de la transition.|  
  
## <a name="remarks"></a>Notes  
 Pendant une transition d’accélération parabolique, la valeur de la variable d’animation passe de la valeur initiale pour la valeur finale se terminant à une rapidité spécifiée. Vous pouvez contrôler la vitesse à laquelle la variable atteigne la valeur finale en spécifiant le taux d’accélération. Car toutes les transitions sont effacées automatiquement, il est recommandé de les allouer à l’aide de nouveau opérateur. L’objet COM IUIAnimationTransition encapsulé est créé par CAnimationController::AnimateGroup, jusqu'à ce que c’est NULL. Modification des variables de membre après que la création de cet objet COM n’a aucun effet.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CParabolicTransitionFromAcceleration](../../mfc/reference/cparabolictransitionfromacceleration-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxanimationcontroller.h  
  
##  <a name="a-namecparabolictransitionfromaccelerationa--cparabolictransitionfromaccelerationcparabolictransitionfromacceleration"></a><a name="cparabolictransitionfromacceleration"></a>CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration  
 Construit une transition d’accélération parabolique et l’initialise avec les paramètres spécifiés.  
  
```  
CParabolicTransitionFromAcceleration(
    DOUBLE dblFinalValue,  
    DOUBLE dblFinalVelocity,  
    DOUBLE dblAcceleration);
```  
  
### <a name="parameters"></a>Paramètres  
 `dblFinalValue`  
 La valeur de la variable d’animation à la fin de la transition.  
  
 `dblFinalVelocity`  
 La rapidité de la variable d’animation à la fin de la transition.  
  
 `dblAcceleration`  
 L’accélération de la variable d’animation pendant la transition.  
  
##  <a name="a-namecreatea--cparabolictransitionfromaccelerationcreate"></a><a name="create"></a>CParabolicTransitionFromAcceleration::Create  
 Appelle la bibliothèque des transitions pour créer l’objet COM de transition encapsulé.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* /* not used */);
```  
  
### <a name="parameters"></a>Paramètres  
 `pLibrary`  
 Pointeur vers la bibliothèque de transitions qui est responsable de la création de transitions standards.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la transition est créée avec succès ; Sinon, FALSE.  
  
##  <a name="a-namemdblaccelerationa--cparabolictransitionfromaccelerationmdblacceleration"></a><a name="m_dblacceleration"></a>CParabolicTransitionFromAcceleration::m_dblAcceleration  
 L’accélération de la variable d’animation pendant la transition.  
  
```  
DOUBLE m_dblAcceleration;  
```  
  
##  <a name="a-namemdblfinalvaluea--cparabolictransitionfromaccelerationmdblfinalvalue"></a><a name="m_dblfinalvalue"></a>CParabolicTransitionFromAcceleration::m_dblFinalValue  
 La valeur de la variable d’animation à la fin de la transition.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="a-namemdblfinalvelocitya--cparabolictransitionfromaccelerationmdblfinalvelocity"></a><a name="m_dblfinalvelocity"></a>CParabolicTransitionFromAcceleration::m_dblFinalVelocity  
 La rapidité de la variable d’animation à la fin de la transition.  
  
```  
DOUBLE m_dblFinalVelocity;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

