---
title: CAnimationVariable, classe | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationVariable::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::Create
- AFXANIMATIONCONTROLLER/CAnimationVariable::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_dblDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_lstTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_pParentObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_variable
dev_langs:
- C++
helpviewer_keywords:
- CAnimationVariable [MFC], CAnimationVariable
- CAnimationVariable [MFC], AddTransition
- CAnimationVariable [MFC], ApplyTransitions
- CAnimationVariable [MFC], ClearTransitions
- CAnimationVariable [MFC], Create
- CAnimationVariable [MFC], CreateTransitions
- CAnimationVariable [MFC], EnableIntegerValueChangedEvent
- CAnimationVariable [MFC], EnableValueChangedEvent
- CAnimationVariable [MFC], GetDefaultValue
- CAnimationVariable [MFC], GetParentAnimationObject
- CAnimationVariable [MFC], GetValue
- CAnimationVariable [MFC], GetVariable
- CAnimationVariable [MFC], SetDefaultValue
- CAnimationVariable [MFC], SetParentAnimationObject
- CAnimationVariable [MFC], m_bAutodestroyTransitions
- CAnimationVariable [MFC], m_dblDefaultValue
- CAnimationVariable [MFC], m_lstTransitions
- CAnimationVariable [MFC], m_pParentObject
- CAnimationVariable [MFC], m_variable
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: efaf47ef434e4f6c63b937d1f360851fa9826e3d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="canimationvariable-class"></a>CAnimationVariable, classe
Représente une variable de l'animation.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CAnimationVariable;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationVariable::CAnimationVariable](#canimationvariable)|Construit un objet de variable de l’animation.|  
|[CAnimationVariable :: ~ CAnimationVariable](#canimationvariable__~canimationvariable)|Destructeur. Appelé lorsqu’un objet CAnimationVariable est détruit.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationVariable::AddTransition](#addtransition)|Ajoute une transition.|  
|[CAnimationVariable::ApplyTransitions](#applytransitions)|Ajoute des transitions à partir de la liste interne de l’animation.|  
|[CAnimationVariable::ClearTransitions](#cleartransitions)|Efface les transitions.|  
|[CAnimationVariable::Create](#create)|Crée l’objet COM sous-jacent animation variable.|  
|[CAnimationVariable::CreateTransitions](#createtransitions)|Crée toutes les transitions à appliquer à cette variable de l’animation.|  
|[CAnimationVariable::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Active ou désactive l’événement IntegerValueChanged.|  
|[CAnimationVariable::EnableValueChangedEvent](#enablevaluechangedevent)|Active ou désactive l’événement ValueChanged.|  
|[CAnimationVariable::GetDefaultValue](#getdefaultvalue)|Retourne la valeur par défaut.|  
|[CAnimationVariable::GetParentAnimationObject](#getparentanimationobject)|Retourne le parent objet d’animation.|  
|[CAnimationVariable::GetValue](#getvalue)|Surchargé. Retourne la valeur actuelle de la variable de l’animation.|  
|[CAnimationVariable::GetVariable](#getvariable)|Retourne un pointeur vers l’objet COM IUIAnimationVariable.|  
|[CAnimationVariable::SetDefaultValue](#setdefaultvalue)|Définit la valeur par défaut et libère l’objet COM IUIAnimationVariable.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationVariable::SetParentAnimationObject](#setparentanimationobject)|Définit la relation entre une variable d’animation et un objet d’animation.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationVariable::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Spécifie si les objets de transition connexes doivent être supprimés.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationVariable::m_dblDefaultValue](#m_dbldefaultvalue)|Spécifie la valeur par défaut, qui est propagée à IUIAnimationVariable.|  
|[CAnimationVariable::m_lstTransitions](#m_lsttransitions)|Contient une liste de transitions qui animer cette variable de l’animation.|  
|[CAnimationVariable::m_pParentObject](#m_pparentobject)|Pointeur vers un objet d’animation qui encapsule cette variable de l’animation.|  
|[CAnimationVariable::m_variable](#m_variable)|Stocke un pointeur vers l’objet COM IUIAnimationVariable. NULL si l’objet COM n’a pas encore été créé, ou si la création a échoué.|  
  
## <a name="remarks"></a>Notes  
 La classe CAnimationVariable encapsule l’objet COM IUIAnimationVariable. Elle contient également une liste de transitions à appliquer à la variable d’animation dans une table de montage séquentiel. Objets CAnimationVariable sont incorporés aux objets d’animation, qui peuvent représenter dans une application une valeur animée, la point, la taille, la couleur et le rectangle.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `CAnimationVariable`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationvariable"></a>  CAnimationVariable :: ~ CAnimationVariable  
 Destructeur. Appelé lorsqu’un objet CAnimationVariable est détruit.  
  
```  
virtual ~CAnimationVariable();
```  
  
##  <a name="addtransition"></a>  CAnimationVariable::AddTransition  
 Ajoute une transition.  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>Paramètres  
 `pTransition`  
 Pointeur vers une transition à ajouter.  
  
### <a name="remarks"></a>Notes  
 Cette méthode est appelée pour ajouter une transition à la liste interne des transitions à appliquer à la variable de l’animation. Cette liste doit être effacée lorsqu’une animation a été planifiée.  
  
##  <a name="applytransitions"></a>  CAnimationVariable::ApplyTransitions  
 Ajoute des transitions à partir de la liste interne de l’animation.  
  
```  
void ApplyTransitions(
    CAnimationController* pController,  
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>Paramètres  
 `pController`  
 Pointeur vers le contrôleur de l’animation parent.  
  
 `pStoryboard`  
 Pointeur vers le storyboard.  
  
 `bDependOnKeyframes`  
 TRUE si cette méthode doit ajouter des transitions qui dépendent des images clés.  
  
### <a name="remarks"></a>Notes  
 Cette méthode ajoute des transitions à partir de la liste interne de l’animation. Elle est appelée à partir du code de niveau supérieur plusieurs fois pour ajouter des transitions qui n’a pas été dépendent des images clés et ajouter des transitions qui dépendent des images clés. Si l’objet COM de la variable d’animation sous-jacente n’a pas été créée, cette méthode crée à ce stade.  
  
##  <a name="canimationvariable"></a>  CAnimationVariable::CAnimationVariable  
 Construit un objet de variable de l’animation.  
  
```  
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```  
  
### <a name="parameters"></a>Paramètres  
 `dblDefaultValue`  
 Spécifie la valeur par défaut.  
  
### <a name="remarks"></a>Notes  
 Construit un objet d’animation variable et définit sa valeur par défaut. Une valeur par défaut est utilisée lorsqu’une variable n’est pas animée ou ne peut pas être animée.  
  
##  <a name="cleartransitions"></a>  CAnimationVariable::ClearTransitions  
 Efface les transitions.  
  
```  
void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>Paramètres  
 `bAutodestroy`  
 Spécifie si cette méthode doit supprimer les objets de transition.  
  
### <a name="remarks"></a>Notes  
 Cette méthode supprime toutes les transitions de la liste interne des transitions. Si bAutodestroy a la valeur TRUE, ou que m_bAutodestroyTransitions a la valeur TRUE, les transitions sont supprimées. Sinon, l’appelant doit libérer des objets de la transition.  
  
##  <a name="create"></a>  CAnimationVariable::Create  
 Crée l’objet COM sous-jacent animation variable.  
  
```  
virtual BOOL Create(IUIAnimationManager* pManager);
```  
  
### <a name="parameters"></a>Paramètres  
 `pManager`  
 Pointeur vers le Gestionnaire d’animations.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la variable d’animation a été créée avec succès ; Sinon, FALSE.  
  
### <a name="remarks"></a>Notes  
 Cette méthode crée l’objet COM de la variable d’animation sous-jacente et définit sa valeur par défaut.  
  
##  <a name="createtransitions"></a>  CAnimationVariable::CreateTransitions  
 Crée toutes les transitions à appliquer à cette variable de l’animation.  
  
```  
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Paramètres  
`pLibrary`  
 Un pointeur vers un [interface IUIAnimationTransitionLibrary](https://msdn.microsoft.com/library/windows/desktop/dd371897), qui définit une bibliothèque de transitions standards.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si les transitions ont été créées avec succès ; Sinon, FALSE.  
  
### <a name="remarks"></a>Notes  
 Cette méthode est appelée par l’infrastructure lorsqu’il a besoin créer des transitions qui ont été ajoutées à la liste interne de la variable de transitions.  
  
##  <a name="enableintegervaluechangedevent"></a>  CAnimationVariable::EnableIntegerValueChangedEvent  
 Active ou désactive l’événement IntegerValueChanged.  
  
```  
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Paramètres  
 `pController`  
 Pointeur vers un contrôleur parent.  
  
 `bEnable`  
 TRUE - activer l’événement, FALSE - désactiver l’événement.  
  
### <a name="remarks"></a>Notes  
 Lorsque l’événement ValueChanged est activé, l’infrastructure appelle la méthode virtuelle CAnimationController::OnAnimationIntegerValueChanged. Vous devez la substituer dans une classe dérivée de CAnimationController pour traiter cet événement. Cette méthode est appelée chaque fois que la valeur entière de la variable de l’animation est modifiée.  
  
##  <a name="enablevaluechangedevent"></a>  CAnimationVariable::EnableValueChangedEvent  
 Active ou désactive l’événement ValueChanged.  
  
```  
void EnableValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Paramètres  
 `pController`  
 Pointeur vers un contrôleur parent.  
  
 `bEnable`  
 TRUE - activer l’événement, FALSE - désactiver l’événement.  
  
### <a name="remarks"></a>Notes  
 Lorsque l’événement ValueChanged est activé, l’infrastructure appelle la méthode virtuelle CAnimationController::OnAnimationValueChanged. Vous devez la substituer dans une classe dérivée de CAnimationController pour traiter cet événement. Cette méthode est appelée chaque fois que la valeur de la variable de l’animation est modifiée.  
  
##  <a name="getdefaultvalue"></a>  CAnimationVariable::GetDefaultValue  
 Retourne la valeur par défaut.  
  
```  
DOUBLE GetDefaultValue() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur par défaut.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette fonction pour obtenir la valeur par défaut de la variable de l’animation. La valeur par défaut peut être définie dans le constructeur ou par méthode SetDefaultValue.  
  
##  <a name="getparentanimationobject"></a>  CAnimationVariable::GetParentAnimationObject  
 Retourne le parent objet d’animation.  
  
```  
CAnimationBaseObject* GetParentAnimationObject();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’objet d’animation parent, si la relation a été établie, sinon NULL.  
  
### <a name="remarks"></a>Notes  
 Cette méthode peut être appelée pour récupérer un pointeur vers un objet d’animation parent (un conteneur).  
  
##  <a name="getvalue"></a>  CAnimationVariable::GetValue  
 Retourne la valeur actuelle de la variable de l’animation.  
  
```  
HRESULT GetValue(DOUBLE& dblValue);  
HRESULT GetValue(INT32& nValue);
```  
  
### <a name="parameters"></a>Paramètres  
 `dblValue`  
 La valeur actuelle de la variable de l’animation.  
  
 `nValue`  
 La valeur actuelle de la variable de l’animation.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si la valeur a été obtenue avec succès, ou la variable d’animation sous-jacente n’a pas été créée. Sinon, code d’erreur HRESULT.  
  
### <a name="remarks"></a>Notes  
 Cette méthode peut être appelée pour extraire la valeur actuelle de la variable de l’animation. Si l’objet COM sous-jacent n’a pas été créé, dblValue contient une valeur par défaut, lorsque la fonction retourne.  
  
##  <a name="getvariable"></a>  CAnimationVariable::GetVariable  
 Retourne un pointeur vers l’objet COM IUIAnimationVariable.  
  
```  
IUIAnimationVariable* GetVariable();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur valide vers l’objet COM IUIAnimationVariable, ou NULL si la variable d’animation n’a été créé, ou ne peut pas être créé.  
  
### <a name="remarks"></a>Notes  
 Cette fonction permet d’accéder à l’objet COM IUIAnimationVariable sous-jacent et appeler ses méthodes directement si nécessaire.  
  
##  <a name="m_bautodestroytransitions"></a>  CAnimationVariable::m_bAutodestroyTransitions  
 Spécifie si les objets de transition connexes doivent être supprimés.  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
### <a name="remarks"></a>Notes  
 Définissez cette valeur sur True pour forcer la suppression des objets de transition lorsqu’ils sont supprimés de la liste interne des transitions. Si cette valeur est FALSE, les transitions doivent être supprimées en appelant l’application. La liste de transitions est toujours effacée une fois qu’une animation a été planifiée. La valeur par défaut est FALSE.  
  
##  <a name="m_dbldefaultvalue"></a>  CAnimationVariable::m_dblDefaultValue  
 Spécifie la valeur par défaut, qui est propagée à IUIAnimationVariable.  
  
```  
DOUBLE m_dblDefaultValue;  
```  
  
##  <a name="m_lsttransitions"></a>  CAnimationVariable::m_lstTransitions  
 Contient une liste de transitions qui animer cette variable de l’animation.  
  
```  
CObList m_lstTransitions;  
```  
  
##  <a name="m_pparentobject"></a>  CAnimationVariable::m_pParentObject  
 Pointeur vers un objet d’animation qui encapsule cette variable de l’animation.  
  
```  
CAnimationBaseObject* m_pParentObject;  
```  
  
##  <a name="m_variable"></a>  CAnimationVariable::m_variable  
 Stocke un pointeur vers l’objet COM IUIAnimationVariable. NULL si l’objet COM n’a pas encore été créé, ou si la création a échoué.  
  
```  
ATL::CComPtr<IUIAnimationVariable> m_variable;  
```  
  
##  <a name="setdefaultvalue"></a>  CAnimationVariable::SetDefaultValue  
 Définit la valeur par défaut et libère l’objet COM IUIAnimationVariable.  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>Paramètres  
 `dblDefaultValue`  
 Spécifie la nouvelle valeur par défaut.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette méthode pour réinitialiser la valeur par défaut. Cette méthode libère l’objet COM IUIAnimationVariable interne, par conséquent, lors de la variable de l’animation est recréé, l’objet COM sous-jacent obtient la nouvelle valeur par défaut. La valeur par défaut est retournée par GetValue si l’objet COM qui représente la variable d’animation n’est pas créé, ou si la variable n’a pas été animée.  
  
##  <a name="setparentanimationobject"></a>  CAnimationVariable::SetParentAnimationObject  
 Définit la relation entre une variable d’animation et un objet d’animation.  
  
```  
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentObject`  
 Pointeur vers un objet d’animation qui contient cette variable.  
  
### <a name="remarks"></a>Notes  
 Cette méthode est appelée en interne pour établir la relation entre une variable d’animation et un objet d’animation qui l’encapsule.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)
