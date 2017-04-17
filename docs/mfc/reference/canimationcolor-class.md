---
title: Classe CAnimationColor | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationColor class
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: e053986737b8e62103666787b99b01cbf19cdc60
ms.lasthandoff: 02/24/2017

---
# <a name="canimationcolor-class"></a>CAnimationColor, classe
Implémente les fonctionnalités d'une couleur dont les composants rouge, vert et bleu peuvent être animés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationColor::CAnimationColor](#canimationcolor)|Surchargé. Construit un objet de couleur de l’animation.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationColor::AddTransition](#addtransition)|Ajoute des transitions pour les composants rouge, vert et bleu.|  
|[CAnimationColor::GetB](#getb)|Fournit l’accès à CAnimationVariable qui représente la composante bleu.|  
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|Retourne les valeurs par défaut pour les composants de couleur.|  
|[CAnimationColor::GetG](#getg)|Fournit l’accès à CAnimationVariable qui représente la composante verte.|  
|[CAnimationColor::GetR](#getr)|Fournit l’accès à CAnimationVariable qui représente la composante rouge.|  
|[CAnimationColor::GetValue](#getvalue)|Retourne la valeur actuelle.|  
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|Définit la valeur par défaut.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|Insère les variables d’animation encapsulées dans une liste. (Substitue [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationColor::operator COLORREF](#operator_colorref)||  
|[CAnimationColor::operator =](#operator_eq)|Affecte la couleur à CAnimationColor.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationColor::m_bValue](#m_bvalue)|La variable d’animation encapsulée qui représente la composante bleue de la couleur d’animation.|  
|[CAnimationColor::m_gValue](#m_gvalue)|La variable d’animation encapsulée qui représente la composante verte de la couleur d’animation.|  
|[CAnimationColor::m_rValue](#m_rvalue)|La variable d’animation encapsulée qui représente la composante rouge de la couleur d’animation.|  
  
## <a name="remarks"></a>Notes  
 La classe CAnimationColor encapsule trois objets CAnimationVariable et peut représenter dans les applications une couleur. Par exemple, vous pouvez utiliser cette classe pour animer des couleurs de n’importe quel objet sur l’écran (comme la couleur du texte, la couleur d’arrière-plan etc.). Pour utiliser cette classe dans l’application, simplement instancier un objet de cette classe, ajoutez-le au contrôleur de l’animation à l’aide de CAnimationController::AddAnimationObject et appeler AddTransition pour chaque transition à appliquer aux composants rouge, vert et bleu.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationColor`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationColor::AddTransition  
 Ajoute des transitions pour les composants rouge, vert et bleu.  
  
```  
void AddTransition(
    CBaseTransition* pRTransition,  
    CBaseTransition* pGTransition,  
    CBaseTransition* pBTransition);
```  
  
### <a name="parameters"></a>Paramètres  
 `pRTransition`  
 Transition pour la composante rouge.  
  
 `pGTransition`  
 Transition pour la composante verte.  
  
 `pBTransition`  
 Transition pour la composante bleue.  
  
### <a name="remarks"></a>Notes  
 Appelez cette fonction pour ajouter les transitions spécifiées à la liste interne des transitions à appliquer aux variables d’animation représentant les composants de couleur. Lorsque vous ajoutez des transitions, ils ne sont pas appliquées immédiatement et stockées dans une liste interne. Les transitions sont appliquées (ajoutée à un storyboard pour une valeur particulière) lorsque vous appelez CAnimationController::AnimateGroup. Si vous n’avez pas besoin d’appliquer une transition à une des composantes de couleur, vous pouvez passer NULL.  
  
##  <a name="canimationcolor"></a>CAnimationColor::CAnimationColor  
 Construit un objet CAnimationColor.  
  
```  
CAnimationColor();
 
CAnimationColor(
    COLORREF color,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `color`  
 Spécifie la couleur par défaut.  
  
 `nGroupID`  
 Spécifie l’ID de groupe.  
  
 `nObjectID`  
 Spécifie l’ID d’objet.  
  
 `dwUserData`  
 Spécifie les données définies par l’utilisateur.  
  
### <a name="remarks"></a>Remarques  
 L’objet est construit avec les valeurs par défaut pour le rouge, vert, bleu, ID d’objet et ID de groupe, qui auront la valeur 0. Ils peuvent être modifiés ultérieurement lors de l’exécution avec SetDefaultValue et SetID.  
  
##  <a name="getanimationvariablelist"></a>CAnimationColor::GetAnimationVariableList  
 Insère les variables d’animation encapsulées dans une liste.  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Paramètres  
 `lst`  
 Lorsque la fonction est retournée, contient des pointeurs aux trois objets CAnimationVariable représentant les composants rouges, verts et bleus.  
  
##  <a name="getb"></a>CAnimationColor::GetB  
 Fournit l’accès à CAnimationVariable qui représente la composante bleu.  
  
```  
CAnimationVariable& GetB();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à CAnimationVariable encapsulée qui représente la composante bleu.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez appeler cette méthode pour accéder directement à l’objet CAnimationVariable sous-jacent représentant la composante bleu.  
  
##  <a name="getdefaultvalue"></a>CAnimationColor::GetDefaultValue  
 Retourne les valeurs par défaut pour les composants de couleur.  
  
```  
COLORREF GetDefaultValue();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur COLORREF qui contient les valeurs par défaut pour les composants RGB.  
  
### <a name="remarks"></a>Notes  
 Appelez cette fonction pour récupérer la valeur par défaut, ce qui a été précédemment définie par le constructeur ou SetDefaultValue.  
  
##  <a name="getg"></a>CAnimationColor::GetG  
 Fournit l’accès à CAnimationVariable qui représente la composante verte.  
  
```  
CAnimationVariable& GetG();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à encapsulé CAnimationVariable représentant la composante vert.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez appeler cette méthode pour obtenir un accès direct au composant vert représentant CAnimationVariable sous-jacent.  
  
##  <a name="getr"></a>CAnimationColor::GetR  
 Fournit l’accès à CAnimationVariable qui représente la composante rouge.  
  
```  
CAnimationVariable& GetR();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à CAnimationVariable encapsulée qui représente la composante rouge.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez appeler cette méthode pour accéder directement à l’objet CAnimationVariable sous-jacent représentant la composante rouge.  
  
##  <a name="getvalue"></a>CAnimationColor::GetValue  
 Retourne la valeur actuelle.  
  
```  
BOOL GetValue(COLORREF& color);
```  
  
### <a name="parameters"></a>Paramètres  
 `color`  
 Sortie. Contient la valeur actuelle lorsque cette méthode est retournée.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la valeur actuelle a été extrait avec succès ; Sinon, FALSE.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction pour extraire la valeur actuelle de la couleur de l’animation. Si cette méthode échoue ou que les objets COM sous-jacents pour les composants de couleur n’ont pas été initialisés, color contient la valeur par défaut, ce qui a été définie précédemment dans le constructeur ou SetDefaultValue.  
  
##  <a name="m_bvalue"></a>CAnimationColor::m_bValue  
 La variable d’animation encapsulée qui représente la composante bleue de la couleur d’animation.  
  
```  
CAnimationVariable m_bValue;  
```  
  
##  <a name="m_gvalue"></a>CAnimationColor::m_gValue  
 La variable d’animation encapsulée qui représente la composante verte de la couleur d’animation.  
  
```  
CAnimationVariable m_gValue;  
```  
  
##  <a name="m_rvalue"></a>CAnimationColor::m_rValue  
 La variable d’animation encapsulée qui représente la composante rouge de la couleur d’animation.  
  
```  
CAnimationVariable m_rValue;  
```  
  
##  <a name="operator_colorref"></a>CAnimationColor::operator COLORREF  
  
```  
operator COLORREF();
```   
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="operator_eq"></a>CAnimationColor::operator =  
 Affecte la couleur à CAnimationColor.  
  
```  
void operator=(COLORREF color);
```  
  
### <a name="parameters"></a>Paramètres  
 `color`  
 Spécifie la nouvelle valeur de couleur d’Animation.  
  
### <a name="remarks"></a>Remarques  
 Il est recommandé du pour faire avant le démarrage de l’animation, parce que cet opérateur appelle SetDefaultValue qui recrée les objets COM sous-jacents pour les composants de couleur s’ils ont été créés. Si vous êtes abonné aux événements (ValueChanged ou IntegerValueChanged), cet objet d’animation, vous devez réactiver ces événements.  
  
##  <a name="setdefaultvalue"></a>CAnimationColor::SetDefaultValue  
 Définit la valeur par défaut.  
  
```  
void SetDefaultValue(COLORREF color);
```  
  
### <a name="parameters"></a>Paramètres  
 `color`  
 Spécifie les nouvelles valeurs par défaut pour les composants rouges, verts et bleus.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette fonction pour définir une valeur par défaut pour l’objet d’animation. Ces méthodes assignent des valeurs par défaut pour les composants de couleur de la couleur d’animation. Il recrée également les objets COM sous-jacents s’ils ont été créés. Si vous êtes abonné aux événements (ValueChanged ou IntegerValueChanged), cet objet d’animation, vous devez réactiver ces événements.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)
