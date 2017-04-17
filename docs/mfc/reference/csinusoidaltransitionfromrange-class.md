---
title: Classe CSinusoidalTransitionFromRange | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMaximumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMinimumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_period
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_slope
dev_langs:
- C++
helpviewer_keywords:
- CSinusoidalTransitionFromRange class
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
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
ms.openlocfilehash: f9dd0e236207c0b4139de42f4c616aaad9dcad28
ms.lasthandoff: 02/24/2017

---
# <a name="csinusoidaltransitionfromrange-class"></a>CSinusoidalTransitionFromRange, classe
Encapsule une transition de plage sinusoïdale comportant une plage d'oscillation donnée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSinusoidalTransitionFromRange : public CBaseTransition;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange](#csinusoidaltransitionfromrange)|Construit un objet de transition.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::Create](#create)|Appelle la bibliothèque des transitions pour créer l’objet COM de transition encapsulé. (Substitue [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::m_dblMaximumValue](#m_dblmaximumvalue)|La valeur de la variable d’animation à une crête de l’onde sinusoïdale.|  
|[CSinusoidalTransitionFromRange::m_dblMinimumValue](#m_dblminimumvalue)|La valeur de la variable d’animation à un bac de l’onde sinusoïdale.|  
|[CSinusoidalTransitionFromRange::m_duration](#m_duration)|La durée de la transition.|  
|[CSinusoidalTransitionFromRange::m_period](#m_period)|La période d’oscillation de l’onde sinusoïdale en secondes.|  
|[CSinusoidalTransitionFromRange::m_slope](#m_slope)|La courbe au début de la transition.|  
  
## <a name="remarks"></a>Remarques  
 La valeur de la variable d’animation fluctue entre les valeurs minimales et maximales spécifiées sur toute la durée d’une transition de plage sinusoïdale. Le paramètre d’inclinaison est utilisé pour lever l’ambiguïté entre les deux ondes sinusoïdales possibles spécifiées par les autres paramètres. Car toutes les transitions sont effacées automatiquement, il est recommandé de les allouer à l’aide de nouveau opérateur. L’objet COM IUIAnimationTransition encapsulé est créé par CAnimationController::AnimateGroup, jusqu'à ce que c’est NULL. Modification des variables de membre après que la création de cet objet COM n’a aucun effet.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromRange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxanimationcontroller.h  
  
##  <a name="create"></a>CSinusoidalTransitionFromRange::Create  
 Appelle la bibliothèque des transitions pour créer l’objet COM de transition encapsulé.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Paramètres  
 `pLibrary`  
 Pointeur vers la bibliothèque de transitions qui est responsable de la création de transitions standards.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la transition est créée avec succès ; Sinon, FALSE.  
  
##  <a name="csinusoidaltransitionfromrange"></a>CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange  
 Construit un objet de transition.  
  
```  
CSinusoidalTransitionFromRange(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE dblMinimumValue,  
    DOUBLE dblMaximumValue,  
    UI_ANIMATION_SECONDS period,  
    UI_ANIMATION_SLOPE slope);
```  
  
### <a name="parameters"></a>Paramètres  
 `duration`  
 La durée de la transition.  
  
 `dblMinimumValue`  
 La valeur de la variable d’animation à un bac de l’onde sinusoïdale.  
  
 `dblMaximumValue`  
 La valeur de la variable d’animation à une crête de l’onde sinusoïdale.  
  
 `period`  
 La période d’oscillation de l’onde sinusoïdale en secondes.  
  
 `slope`  
 La courbe au début de la transition.  
  
##  <a name="m_dblmaximumvalue"></a>CSinusoidalTransitionFromRange::m_dblMaximumValue  
 La valeur de la variable d’animation à une crête de l’onde sinusoïdale.  
  
```  
DOUBLE m_dblMaximumValue;  
```  
  
##  <a name="m_dblminimumvalue"></a>CSinusoidalTransitionFromRange::m_dblMinimumValue  
 La valeur de la variable d’animation à un bac de l’onde sinusoïdale.  
  
```  
DOUBLE m_dblMinimumValue;  
```  
  
##  <a name="m_duration"></a>CSinusoidalTransitionFromRange::m_duration  
 La durée de la transition.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_period"></a>CSinusoidalTransitionFromRange::m_period  
 La période d’oscillation de l’onde sinusoïdale en secondes.  
  
```  
UI_ANIMATION_SECONDS m_period;  
```  
  
##  <a name="m_slope"></a>CSinusoidalTransitionFromRange::m_slope  
 La courbe au début de la transition.  
  
```  
UI_ANIMATION_SLOPE m_slope;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)
