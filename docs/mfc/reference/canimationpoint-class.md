---
title: CAnimationPoint, classe | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetX
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetY
- AFXANIMATIONCONTROLLER/CAnimationPoint::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_xValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_yValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationPoint [MFC], CAnimationPoint
- CAnimationPoint [MFC], AddTransition
- CAnimationPoint [MFC], GetDefaultValue
- CAnimationPoint [MFC], GetValue
- CAnimationPoint [MFC], GetX
- CAnimationPoint [MFC], GetY
- CAnimationPoint [MFC], SetDefaultValue
- CAnimationPoint [MFC], GetAnimationVariableList
- CAnimationPoint [MFC], m_xValue
- CAnimationPoint [MFC], m_yValue
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f7b81c49ce96fd026cd1974e505ac50dec131611
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="canimationpoint-class"></a>CAnimationPoint, classe
Implémente les fonctionnalités d'un point dont les coordonnées peuvent être animées.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CAnimationPoint : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationPoint::CAnimationPoint](#canimationpoint)|Surchargé. Construit un objet CAnimationPoint.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationPoint::AddTransition](#addtransition)|Ajoute des transitions pour X et Y coordonnées.|  
|[CAnimationPoint::GetDefaultValue](#getdefaultvalue)|Retourne les valeurs par défaut pour X et Y coordonnées.|  
|[CAnimationPoint::GetValue](#getvalue)|Retourne la valeur actuelle.|  
|[CAnimationPoint::GetX](#getx)|Fournit l’accès à CAnimationVariable pour coordonnée X.|  
|[CAnimationPoint::GetY](#gety)|Fournit l’accès à CAnimationVariable pour la coordonnée Y.|  
|[CAnimationPoint::SetDefaultValue](#setdefaultvalue)|Définit la valeur par défaut.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationPoint::GetAnimationVariableList](#getanimationvariablelist)|Insère les variables d’animation encapsulées dans une liste. (Substitue [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationPoint::operator CPoint](#operator_cpoint)|Convertit CAnimationPoint CPoint.|  
|[CAnimationPoint::operator =](#operator_eq)|Assigne ptSrc à CAnimationPoint.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationPoint::m_xValue](#m_xvalue)|La variable d’animation encapsulée qui représente X coordonnées du point de l’animation.|  
|[CAnimationPoint::m_yValue](#m_yvalue)|La variable d’animation encapsulée qui représente la coordonnée Y du point de l’animation.|  
  
## <a name="remarks"></a>Notes  
 La classe CAnimationPoint encapsule deux objets CAnimationVariable et peut représenter dans les applications d’un point. Par exemple, vous pouvez utiliser cette classe pour animer une position d’un objet à l’écran (par exemple, la chaîne de texte, cercle, point, etc.). Pour utiliser cette classe dans l’application, uniquement instancier un objet de cette classe, ajoutez-le au contrôleur de l’animation à l’aide de CAnimationController::AddAnimationObject et appeler AddTransition pour chaque transition à appliquer aux coordonnées X et/ou Y.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationPoint`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>  CAnimationPoint::AddTransition  
 Ajoute des transitions pour X et Y coordonnées.  
  
```  
void AddTransition(
    CBaseTransition* pXTransition,  
    CBaseTransition* pYTransition);
```  
  
### <a name="parameters"></a>Paramètres  
 `pXTransition`  
 Pointeur vers la transition pour les coordonnées X.  
  
 `pYTransition`  
 Un pointeur vers la transition pour Y coordonnée.  
  
### <a name="remarks"></a>Notes  
 Appelez cette fonction pour ajouter les transitions spécifiées à la liste interne des transitions à appliquer aux variables d’animation pour X et Y coordonnées. Lorsque vous ajoutez des transitions, elles ne sont pas appliquées immédiatement et stockées dans une liste interne. Transitions sont appliquées (ajoutée à une table de montage séquentiel pour une valeur particulière) lorsque vous appelez CAnimationController::AnimateGroup. Si vous n’avez pas besoin d’appliquer une transition à une des coordonnées, vous pouvez passer NULL.  
  
##  <a name="canimationpoint"></a>  CAnimationPoint::CAnimationPoint  
 Construit un objet CAnimationPoint.  
  
```  
CAnimationPoint();

 
CAnimationPoint(
    const CPoint& ptDefault,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `ptDefault`  
 Spécifie les coordonnées de point par défaut.  
  
 `nGroupID`  
 Spécifie l’ID de groupe.  
  
 `nObjectID`  
 Spécifie l’ID d’objet.  
  
 `dwUserData`  
 Spécifie les données définies par l’utilisateur.  
  
### <a name="remarks"></a>Notes  
 Construit un objet CAnimationPoint avec les propriétés par défaut : les coordonnées de point par défaut, ID de groupe et ID d’objet sont égales à 0.  
  
##  <a name="getanimationvariablelist"></a>  CAnimationPoint::GetAnimationVariableList  
 Insère les variables d’animation encapsulées dans une liste.  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Paramètres  
 `lst`  
 Lorsque la fonction est retournée, contient des pointeurs aux deux objets CAnimationVariable représentant les coordonnées X et Y.  
  
##  <a name="getdefaultvalue"></a>  CAnimationPoint::GetDefaultValue  
 Retourne les valeurs par défaut pour X et Y coordonnées.  
  
```  
CPoint GetDefaultValue();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un point de conteneur par défaut.  
  
### <a name="remarks"></a>Notes  
 Appelez cette fonction pour récupérer la valeur par défaut, ce qui a été définie précédemment par le constructeur ou SetDefaultValue.  
  
##  <a name="getvalue"></a>  CAnimationPoint::GetValue  
 Retourne la valeur actuelle.  
  
```  
BOOL GetValue(CPoint& ptValue);
```  
  
### <a name="parameters"></a>Paramètres  
 `ptValue`  
 Sortie. Contient la valeur actuelle lorsque cette méthode est retournée.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la valeur actuelle a été correctement récupérée ; Sinon, FALSE.  
  
### <a name="remarks"></a>Notes  
 Appelez cette fonction pour récupérer la valeur actuelle du point d’animation. Si cette méthode échoue ou le COM sous-jacente objets x et Y coordonnées n’ont pas été initialisées, ptValue contient la valeur par défaut, ce qui a été définie précédemment dans le constructeur ou SetDefaultValue.  
  
##  <a name="getx"></a>  CAnimationPoint::GetX  
 Fournit l’accès à CAnimationVariable pour coordonnée X.  
  
```  
CAnimationVariable& GetX();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à CAnimationVariable encapsulée qui représente X coordonner.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez appeler cette méthode pour obtenir un accès direct à l’objet CAnimationVariable sous-jacent représentant X coordonner.  
  
##  <a name="gety"></a>  CAnimationPoint::GetY  
 Fournit l’accès à CAnimationVariable pour la coordonnée Y.  
  
```  
CAnimationVariable& GetY();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à CAnimationVariable encapsulée qui représente la coordonnée Y.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez appeler cette méthode pour obtenir un accès direct à CAnimationVariable sous-jacent qui représente la coordonnée Y.  
  
##  <a name="m_xvalue"></a>  CAnimationPoint::m_xValue  
 La variable d’animation encapsulée qui représente X coordonnées du point de l’animation.  
  
```  
CAnimationVariable m_xValue;  
```  
  
##  <a name="m_yvalue"></a>  CAnimationPoint::m_yValue  
 La variable d’animation encapsulée qui représente la coordonnée Y du point de l’animation.  
  
```  
CAnimationVariable m_yValue;  
```  
  
##  <a name="operator_cpoint"></a>  CAnimationPoint::operator CPoint  
 Convertit CAnimationPoint CPoint.  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>Valeur de retour  
 Valeur actuelle de l’objet CAnimationPoint comme CPoint.  
  
### <a name="remarks"></a>Notes  
 Cette fonction a appelle GetValue en interne. Si GetValue échoue pour une raison quelconque, le point retourné contient les valeurs par défaut pour X et Y coordonnées.  
  
##  <a name="operator_eq"></a>  CAnimationPoint::operator =  
 Assigne ptSrc à CAnimationPoint.  
  
```  
void operator=(const CPoint& ptSrc);
```  
  
### <a name="parameters"></a>Paramètres  
 `ptSrc`  
 Fait référence à CPoint ou POINT.  
  
### <a name="remarks"></a>Notes  
 Assigne ptSrc à CAnimationPoint. Il est recommandé d’effectuer qu’avant le démarrage de l’animation, parce que cet opérateur appelle SetDefaultValue qui recrée le modèle COM sous-jacente des objets pour les coordonnées X et Y si elles ont été créées. Si vous êtes inscrit cet objet d’animation aux événements (ValueChanged ou IntegerValueChanged), vous devez réactiver ces événements.  
  
##  <a name="setdefaultvalue"></a>  CAnimationPoint::SetDefaultValue  
 Définit la valeur par défaut.  
  
```  
void SetDefaultValue(const POINT& ptDefault);
```  
  
### <a name="parameters"></a>Paramètres  
 `ptDefault`  
 Spécifie la valeur de point par défaut.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette fonction pour définir une valeur par défaut pour l’objet d’animation. Cette valeur par défaut de méthodes assigne des valeurs à des coordonnées X et Y du point de l’animation. Il recrée également les objets COM sous-jacents s’ils ont été créés. Si vous êtes inscrit cet objet d’animation aux événements (ValueChanged ou IntegerValueChanged), vous devez réactiver ces événements.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)
