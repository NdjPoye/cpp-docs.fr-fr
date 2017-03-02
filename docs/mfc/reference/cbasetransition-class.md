---
title: Classe CBaseTransition | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBaseTransition
- afxanimationcontroller/CBaseTransition
dev_langs:
- C++
helpviewer_keywords:
- CBaseTransition class
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
caps.latest.revision: 17
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b979d03587ada42486d0462733dfe6fd22f9f7cc
ms.lasthandoff: 02/24/2017

---
# <a name="cbasetransition-class"></a>CBaseTransition, classe
Représente une transition de base.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CBaseTransition : public CObject;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-enumerations"></a>Énumérations publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Énumération CBaseTransition::TRANSITION_TYPE](#transition_type_enumeration)|Définit les types de transition actuellement pris en charge par l’implémentation MFC de l’API Animation Windows.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CBaseTransition::CBaseTransition](#cbasetransition)|Construit un objet de base de la transition.|  
|[CBaseTransition :: ~ CBaseTransition](#cbasetransition__~cbasetransition)|Destructeur. Appelé lorsqu’un objet de transition est détruit.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CBaseTransition::AddToStoryboard](#addtostoryboard)|Ajoute une transition à un storyboard.|  
|[CBaseTransition::AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|Ajoute une transition à un storyboard.|  
|[CBaseTransition::Clear](#clear)|Les versions d’objet COM IUIAnimationTransition encapsulé.|  
|[CBaseTransition::Create](#create)|Crée une transition COM.|  
|[CBaseTransition::GetEndKeyframe](#getendkeyframe)|Renvoie la première image clé.|  
|[CBaseTransition::GetRelatedVariable](#getrelatedvariable)|Retourne un pointeur vers la variable connexe.|  
|[CBaseTransition::GetStartKeyframe](#getstartkeyframe)|Renvoie la première image clé.|  
|[CBaseTransition::GetTransition](#gettransition)|Surchargé. Retourne un pointeur vers un objet de transition COM sous-jacent.|  
|[CBaseTransition::GetType](#gettype)|Retourne le type de transition.|  
|[CBaseTransition::IsAdded](#isadded)|Indique si une transition a été ajoutée à un storyboard.|  
|[CBaseTransition::SetKeyframes](#setkeyframes)|Définit des images clés pour une transition.|  
|[CBaseTransition::SetRelatedVariable](#setrelatedvariable)|Établit une relation entre la variable de l’animation et de transition.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CBaseTransition::m_bAdded](#m_badded)|Spécifie si une transition a été ajoutée à un storyboard.|  
|[CBaseTransition::m_pEndKeyframe](#m_pendkeyframe)|Stocke un pointeur vers l’image clé spécifie la fin de la transition.|  
|[CBaseTransition::m_pRelatedVariable](#m_prelatedvariable)|Pointeur vers une variable d’animation qui est animée avec la transition stockée dans m_transition.|  
|[CBaseTransition::m_pStartKeyframe](#m_pstartkeyframe)|Stocke un pointeur vers l’image clé qui spécifie le début de la transition.|  
|[CBaseTransition::m_transition](#m_transition)|Stocke un pointeur à IUIAnimationTransition. NULL si un objet de transition COM n’a pas été créé.|  
|[CBaseTransition::m_type](#m_type)|Stocke le type de transition.|  
  
## <a name="remarks"></a>Notes  
 Cette classe encapsule l’interface IUIAnimationTransition et sert de classe de base pour toutes les transitions.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CBaseTransition`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxanimationcontroller.h  
  
##  <a name="a-namedtorcbasetransitiona--cbasetransitioncbasetransition"></a><a name="_dtorcbasetransition"></a>CBaseTransition :: ~ CBaseTransition  
 Destructeur. Appelé lorsqu’un objet de transition est détruit.  
  
```  
virtual ~CBaseTransition();
```  
  
##  <a name="a-nameaddtostoryboarda--cbasetransitionaddtostoryboard"></a><a name="addtostoryboard"></a>CBaseTransition::AddToStoryboard  
 Ajoute une transition à un storyboard.  
  
```  
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Paramètres  
 `pStoryboard`  
 Pointeur vers le storyboard qui animera la variable connexe.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la transition a été ajoutée à un storyboard.  
  
### <a name="remarks"></a>Notes  
 Applique la transition à la variable connexe dans la table de montage séquentiel. S’il s’agit de la première transition appliquée à cette variable dans ce storyboard, la transition commence au début de la table de montage séquentiel. Sinon, la transition est ajoutée à la dernière transition ajoutée à la variable.  
  
##  <a name="a-nameaddtostoryboardatkeyframesa--cbasetransitionaddtostoryboardatkeyframes"></a><a name="addtostoryboardatkeyframes"></a>CBaseTransition::AddToStoryboardAtKeyframes  
 Ajoute une transition à un storyboard.  
  
```  
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Paramètres  
 `pStoryboard`  
 Pointeur vers le storyboard qui animera la variable connexe.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la transition a été ajoutée à un storyboard.  
  
### <a name="remarks"></a>Notes  
 Applique la transition à la variable connexe dans la table de montage séquentiel. Si l’image clé de démarrage a été spécifiée, la transition commence à cette image clé. Si l’image clé de fin a été spécifiée, la transition commence à l’image clé de démarrage et s’arrête à l’image clé de fin. Si la transition a été créée avec un paramètre de durée spécifié, cette durée est remplacée par la durée de temps entre les images clés de début et de fin. Si aucune image clé n’a été spécifiée, la transition est ajoutée à la dernière transition ajoutée à la variable.  
  
##  <a name="a-namecbasetransitiona--cbasetransitioncbasetransition"></a><a name="cbasetransition"></a>CBaseTransition::CBaseTransition  
 Construit un objet de base de la transition.  
  
```  
CBaseTransition();
```  
  
##  <a name="a-namecleara--cbasetransitionclear"></a><a name="clear"></a>CBaseTransition::Clear  
 Les versions d’objet COM IUIAnimationTransition encapsulé.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Remarques  
 Cette méthode doit être appelée à partir de la méthode de création d’une classe dérivée afin d’éviter la fuite de l’interface IUITransition.  
  
##  <a name="a-namecreatea--cbasetransitioncreate"></a><a name="create"></a>CBaseTransition::Create  
 Crée une transition COM.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory) = 0;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pLibrary`  
 Pointeur vers la bibliothèque de transitions qui crée des transitions standard. Il peut être NULL pour les transitions personnalisées.  
  
 `pFactory`  
 Pointeur vers la fabrique de transitions qui crée des transitions personnalisées. Il peut être NULL pour les transitions standard.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si un objet de transition COM a été créé avec succès ; Sinon, FALSE.  
  
### <a name="remarks"></a>Remarques  
 Il s’agit d’une fonction virtuelle pure qui doit être substituée dans une classe dérivée. Elle est appelée par l’infrastructure pour instancier l’objet de transition COM sous-jacent.  
  
##  <a name="a-namegetendkeyframea--cbasetransitiongetendkeyframe"></a><a name="getendkeyframe"></a>CBaseTransition::GetEndKeyframe  
 Renvoie la première image clé.  
  
```  
CBaseKeyFrame* GetEndKeyframe();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur valide vers une image clé, ou NULL si une transition ne doit pas être insérée entre les images clés.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode peut être utilisée pour accéder à un objet d’image clé qui a été précédemment défini par SetKeyframes. Elle est appelée par le code de niveau supérieur lorsque les transitions sont ajoutées au storyboard.  
  
##  <a name="a-namegetrelatedvariablea--cbasetransitiongetrelatedvariable"></a><a name="getrelatedvariable"></a>CBaseTransition::GetRelatedVariable  
 Retourne un pointeur vers la variable connexe.  
  
```  
CAnimationVariable* GetRelatedVariable();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur valide vers la variable de l’animation, ou NULL si une variable d’animation n’a pas été définie par SetRelatedVariable.  
  
### <a name="remarks"></a>Remarques  
 Il s’agit d’un accesseur à une variable d’animation connexe.  
  
##  <a name="a-namegetstartkeyframea--cbasetransitiongetstartkeyframe"></a><a name="getstartkeyframe"></a>CBaseTransition::GetStartKeyframe  
 Renvoie la première image clé.  
  
```  
CBaseKeyFrame* GetStartKeyframe();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur valide vers une image clé, ou NULL si une transition ne doit pas démarrer après une image clé.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode peut être utilisée pour accéder à un objet d’image clé qui a été précédemment défini par SetKeyframes. Elle est appelée par le code de niveau supérieur lorsque les transitions sont ajoutées au storyboard.  
  
##  <a name="a-namegettransitiona--cbasetransitiongettransition"></a><a name="gettransition"></a>CBaseTransition::GetTransition  
 Retourne un pointeur vers un objet de transition COM sous-jacent.  
  
```  
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory);  
  
IUIAnimationTransition* GetTransition();
```  
  
### <a name="parameters"></a>Paramètres  
 `pLibrary`  
 Pointeur vers la bibliothèque de transitions qui crée des transitions standard. Il peut être NULL pour les transitions personnalisées.  
  
 `pFactory`  
 Pointeur vers la fabrique de transitions qui crée des transitions personnalisées. Il peut être NULL pour les transitions standard.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur valide à IUIAnimationTransition ou NULL si la transition sous-jacente ne peut pas être créé.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode retourne un pointeur vers un objet de transition COM sous-jacent et crée si nécessaire.  
  
##  <a name="a-namegettypea--cbasetransitiongettype"></a><a name="gettype"></a>CBaseTransition::GetType  
 Retourne le type de transition.  
  
```  
TRANSITION_TYPE GetType() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un des TRANSITION_TYPE valeurs énumérées.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode peut être utilisée pour identifier un objet de transition par son type. Le type est défini dans un constructeur dans une classe dérivée.  
  
##  <a name="a-nameisaddeda--cbasetransitionisadded"></a><a name="isadded"></a>CBaseTransition::IsAdded  
 Indique si une transition a été ajoutée à un storyboard.  
  
```  
BOOL IsAdded();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE si une transition a été ajoutée à un storyboard, sinon FALSE.  
  
### <a name="remarks"></a>Remarques  
 Cet indicateur est défini en interne lorsque le code de niveau supérieur ajoute des transitions au storyboard.  
  
##  <a name="a-namembaddeda--cbasetransitionmbadded"></a><a name="m_badded"></a>CBaseTransition::m_bAdded  
 Spécifie si une transition a été ajoutée à un storyboard.  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="a-namempendkeyframea--cbasetransitionmpendkeyframe"></a><a name="m_pendkeyframe"></a>CBaseTransition::m_pEndKeyframe  
 Stocke un pointeur vers l’image clé spécifie la fin de la transition.  
  
```  
CBaseKeyFrame* m_pEndKeyframe;  
```  
  
##  <a name="a-namemprelatedvariablea--cbasetransitionmprelatedvariable"></a><a name="m_prelatedvariable"></a>CBaseTransition::m_pRelatedVariable  
 Pointeur vers une variable d’animation qui est animée avec la transition stockée dans m_transition.  
  
```  
CAnimationVariable* m_pRelatedVariable;  
```  
  
##  <a name="a-namempstartkeyframea--cbasetransitionmpstartkeyframe"></a><a name="m_pstartkeyframe"></a>CBaseTransition::m_pStartKeyframe  
 Stocke un pointeur vers l’image clé qui spécifie le début de la transition.  
  
```  
CBaseKeyFrame* m_pStartKeyframe;  
```  
  
##  <a name="a-namemtransitiona--cbasetransitionmtransition"></a><a name="m_transition"></a>CBaseTransition::m_transition  
 Stocke un pointeur à IUIAnimationTransition. NULL si un objet de transition COM n’a pas été créé.  
  
```  
ATL::CComPtr<IUIAnimationTransition> m_transition;  
```  
  
##  <a name="a-namemtypea--cbasetransitionmtype"></a><a name="m_type"></a>CBaseTransition::m_type  
 Stocke le type de transition.  
  
```  
TRANSITION_TYPE m_type;  
```  
  
##  <a name="a-namesetkeyframesa--cbasetransitionsetkeyframes"></a><a name="setkeyframes"></a>CBaseTransition::SetKeyframes  
 Définit des images clés pour une transition.  
  
```  
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,  
    CBaseKeyFrame* pEnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pStart`  
 Une image clé qui spécifie le début de la transition.  
  
 `pEnd`  
 Une image clé qui spécifie la fin de la transition.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode indique à la transition de démarrer après l’image clé spécifiée et, éventuellement, si pEnd n’est pas NULL, se terminer avant l’image clé spécifiée. Si la transition a été créée avec un paramètre de durée spécifié, cette durée est remplacée par la durée de temps entre les images clés de début et de fin.  
  
##  <a name="a-namesetrelatedvariablea--cbasetransitionsetrelatedvariable"></a><a name="setrelatedvariable"></a>CBaseTransition::SetRelatedVariable  
 Établit une relation entre la variable de l’animation et de transition.  
  
```  
void SetRelatedVariable(CAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>Paramètres  
 `pVariable`  
 Pointeur vers la variable d’animation connexe.  
  
### <a name="remarks"></a>Remarques  
 Établit une relation entre la variable de l’animation et de transition. Une transition peut être appliquée uniquement à une variable.  
  
##  <a name="a-nametransitiontypeenumerationa--cbasetransitiontransitiontype-enumeration"></a><a name="transition_type_enumeration"></a>Énumération CBaseTransition::TRANSITION_TYPE  
 Définit les types de transition actuellement pris en charge par l’implémentation MFC de l’API Animation Windows.  
  
```  
enum TRANSITION_TYPE;  
```  
  
### <a name="remarks"></a>Notes  
 Un type de transition est défini dans le constructeur de transition spécifique. Par exemple, CSinusoidalTransitionFromRange définit son type avec la valeur SINUSOIDAL_FROM_RANGE.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

