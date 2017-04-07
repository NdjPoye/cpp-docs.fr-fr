---
title: Classe CAnimationSize | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCX
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCY
- AFXANIMATIONCONTROLLER/CAnimationSize::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetValue
- AFXANIMATIONCONTROLLER/CAnimationSize::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cxValue
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cyValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationSize class
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
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
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: 84b9ae3b81f72f6c0ae8e88f78357c29e8d82ffd
ms.lasthandoff: 02/24/2017

---
# <a name="canimationsize-class"></a>CAnimationSize, classe
Implémente les fonctionnalités d'un objet taille dont les dimensions peuvent être animées.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CAnimationSize : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationSize::CAnimationSize](#canimationsize)|Surchargé. Construit un objet d’animation taille.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationSize::AddTransition](#addtransition)|Ajoute des transitions pour largeur et hauteur.|  
|[CAnimationSize::GetCX](#getcx)|Fournit l’accès à CAnimationVariable qui représente la largeur.|  
|[CAnimationSize::GetCY](#getcy)|Fournit l’accès à CAnimationVariable qui représente la hauteur.|  
|[CAnimationSize::GetDefaultValue](#getdefaultvalue)|Retourne les valeurs par défaut pour la largeur et hauteur.|  
|[CAnimationSize::GetValue](#getvalue)|Retourne la valeur actuelle.|  
|[CAnimationSize::SetDefaultValue](#setdefaultvalue)|Définit la valeur par défaut.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationSize::GetAnimationVariableList](#getanimationvariablelist)|Insère les variables d’animation encapsulées dans une liste. (Substitue [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationSize::operator CSize](#operator_csize)|Convertit CAnimationSize CSize.|  
|[CAnimationSize::operator =](#operator_eq)|Assigne szSrc à CAnimationSize.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationSize::m_cxValue](#m_cxvalue)|La variable d’animation encapsulée qui représente la largeur de la taille de l’animation.|  
|[CAnimationSize::m_cyValue](#m_cyvalue)|La variable d’animation encapsulée qui représente la hauteur de la taille de l’animation.|  
  
## <a name="remarks"></a>Remarques  
 La classe CAnimationSize encapsule deux objets CAnimationVariable et peut représenter dans les applications une taille. Par exemple, vous pouvez utiliser cette classe pour animer une taille de n’importe quel objet bidimensionnel sur l’écran (comme un rectangle, contrôler etc.). Pour utiliser cette classe dans l’application, simplement instancier un objet de cette classe, ajoutez-le au contrôleur de l’animation à l’aide de CAnimationController::AddAnimationObject et appeler AddTransition pour chaque transition à appliquer à la largeur ou hauteur.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationSize` 
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationSize::AddTransition  
 Ajoute des transitions pour largeur et hauteur.  
  
```  
void AddTransition(
    CBaseTransition* pCXTransition,  
    CBaseTransition* pCYTransition);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCXTransition`  
 Pointeur vers la transition pour la largeur.  
  
 `pCYTransition`  
 Pointeur vers la transition pour la hauteur.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction pour ajouter les transitions spécifiées à la liste interne des transitions à appliquer aux variables d’animation pour la largeur et hauteur. Lorsque vous ajoutez des transitions, ils ne sont pas appliquées immédiatement et stockées dans une liste interne. Les transitions sont appliquées (ajoutée à un storyboard pour une valeur particulière) lorsque vous appelez CAnimationController::AnimateGroup. Si vous n’avez pas besoin d’appliquer une transition à une des dimensions, vous pouvez passer NULL.  
  
##  <a name="canimationsize"></a>CAnimationSize::CAnimationSize  
 Construit un objet d’animation taille.  
  
```  
CAnimationSize();

 
CAnimationSize(
    const CSize& szDefault,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `szDefault`  
 Spécifie la taille par défaut.  
  
 `nGroupID`  
 Spécifie l’ID de groupe.  
  
 `nObjectID`  
 Spécifie l’ID d’objet.  
  
 `dwUserData`  
 Spécifie les données définies par l’utilisateur.  
  
### <a name="remarks"></a>Remarques  
 L’objet est construit avec les valeurs par défaut pour la largeur, hauteur, ID d’objet et ID de groupe, qui auront la valeur 0. Ils peuvent être modifiés ultérieurement lors de l’exécution avec SetDefaultValue et SetID.  
  
##  <a name="getanimationvariablelist"></a>CAnimationSize::GetAnimationVariableList  
 Insère les variables d’animation encapsulées dans une liste.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Paramètres  
 `lst`  
 Lorsque la fonction est retournée, contient des pointeurs aux deux objets CAnimationVariable représentant la largeur et la hauteur.  
  
##  <a name="getcx"></a>CAnimationSize::GetCX  
 Fournit l’accès à CAnimationVariable qui représente la largeur.  
  
```  
CAnimationVariable& GetCX();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à CAnimationVariable encapsulée qui représente la largeur.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez appeler cette méthode pour accéder directement à l’objet CAnimationVariable sous-jacent représentant la largeur.  
  
##  <a name="getcy"></a>CAnimationSize::GetCY  
 Fournit l’accès à CAnimationVariable qui représente la hauteur.  
  
```  
CAnimationVariable& GetCY();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à CAnimationVariable encapsulée qui représente la hauteur.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez appeler cette méthode pour accéder directement à l’objet CAnimationVariable sous-jacent représentant la hauteur.  
  
##  <a name="getdefaultvalue"></a>CAnimationSize::GetDefaultValue  
 Retourne les valeurs par défaut pour la largeur et hauteur.  
  
```  
CSize GetDefaultValue();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Objet CSize qui contient les valeurs par défaut.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction pour récupérer la valeur par défaut, ce qui a été précédemment définie par le constructeur ou SetDefaultValue.  
  
##  <a name="getvalue"></a>CAnimationSize::GetValue  
 Retourne la valeur actuelle.  
  
```  
BOOL GetValue(CSize& szValue);
```  
  
### <a name="parameters"></a>Paramètres  
 `szValue`  
 Sortie. Contient la valeur actuelle lorsque cette méthode est retournée.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la valeur actuelle a été extrait avec succès ; Sinon, FALSE.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction pour extraire la valeur actuelle de la taille de l’animation. Si cette méthode échoue ou que les objets COM sous-jacents pour la largeur et la taille n’ont pas été initialisés, szValue contient la valeur par défaut, ce qui a été définie précédemment dans le constructeur ou SetDefaultValue.  
  
##  <a name="m_cxvalue"></a>CAnimationSize::m_cxValue  
 La variable d’animation encapsulée qui représente la largeur de la taille de l’animation.  
  
```  
CAnimationVariable m_cxValue;  
```  
  
##  <a name="m_cyvalue"></a>CAnimationSize::m_cyValue  
 La variable d’animation encapsulée qui représente la hauteur de la taille de l’animation.  
  
```  
CAnimationVariable m_cyValue;  
```  
  
##  <a name="operator_csize"></a>CAnimationSize::operator CSize  
 Convertit CAnimationSize CSize.  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>Valeur de retour  
 Valeur actuelle de la taille de l’animation CSize.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction a appelle GetValue en interne. Si GetValue échoue pour une raison quelconque, la taille retournée contient les valeurs par défaut pour la largeur et hauteur.  
  
##  <a name="operator_eq"></a>CAnimationSize::operator =  
 Assigne szSrc à CAnimationSize.  
  
```  
void operator=(const CSize& szSrc);
```  
  
### <a name="parameters"></a>Paramètres  
 `szSrc`  
 Fait référence à CSize ou SIZE.  
  
### <a name="remarks"></a>Remarques  
 Assigne szSrc à CAnimationSize. Il est recommandé du pour faire avant le démarrage de l’animation, parce que cet opérateur appelle SetDefaultValue qui recrée les objets COM sous-jacents pour la largeur et la hauteur si elles ont été créées. Si vous êtes abonné aux événements (ValueChanged ou IntegerValueChanged), cet objet d’animation, vous devez réactiver ces événements.  
  
##  <a name="setdefaultvalue"></a>CAnimationSize::SetDefaultValue  
 Définit la valeur par défaut.  
  
```  
void SetDefaultValue(const CSize& szDefault);
```  
  
### <a name="parameters"></a>Paramètres  
 `szDefault`  
 Spécifie la nouvelle taille par défaut.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette fonction pour définir une valeur par défaut pour l’objet d’animation. Ces méthodes assignent des valeurs par défaut pour la largeur et la hauteur de la taille de l’animation. Il recrée également les objets COM sous-jacents s’ils ont été créés. Si vous êtes abonné aux événements (ValueChanged ou IntegerValueChanged), cet objet d’animation, vous devez réactiver ces événements.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

