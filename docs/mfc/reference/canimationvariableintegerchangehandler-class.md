---
title: Classe CAnimationVariableIntegerChangeHandler | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationVariableIntegerChangeHandler class
ms.assetid: 6ac8e91b-e514-4ff6-babd-33f77c4b2b61
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 41062ddcf01d26a4897b7e7ab2fe254bca8a1b5d
ms.lasthandoff: 02/24/2017

---
# <a name="canimationvariableintegerchangehandler-class"></a>CAnimationVariableIntegerChangeHandler, classe
Implémente un rappel, qui est appelé par l'API d'animation lorsque la valeur d'une variable de l'animation est modifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CAnimationVariableIntegerChangeHandler : public CUIAnimationVariableIntegerChangeHandlerBase<CAnimationVariableIntegerChangeHandler>;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler](#canimationvariableintegerchangehandler)|Construit un objet `CAnimationVariableIntegerChangeHandler`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationVariableIntegerChangeHandler::CreateInstance](#createinstance)|Crée une instance de `CAnimationVariableIntegerChangeHandler` rappel.|  
|[CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged](#onintegervaluechanged)|Appelé lorsqu’une valeur d’une variable d’animation a changé. (Substitue `CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged`.)|  
|[CAnimationVariableIntegerChangeHandler::SetAnimationController](#setanimationcontroller)|Stocke un pointeur vers le contrôleur de l’animation pour acheminer les événements.|  
  
## <a name="remarks"></a>Notes  
 Ce gestionnaire d’événements est créé et transmis à la méthode IUIAnimationVariable::SetVariableIntegerChangeHandler, lorsque vous appelez CAnimationVariable::EnableIntegerValueChangedEvent ou CAnimationBaseObject::EnableIntegerValueChangedEvent (qui active cet événement pour toutes les variables d’animation encapsulées dans un objet d’animation).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [Classes MFC](../../mfc/reference/mfc-classes.md)  
  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableIntegerChangeHandlerBase`  
  
 `CAnimationVariableIntegerChangeHandler`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxanimationcontroller.h  
  
##  <a name="canimationvariableintegerchangehandler"></a>CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler  
 Construit un objet CAnimationVariableIntegerChangeHandler.  
  
```  
CAnimationVariableIntegerChangeHandler ();
```  
  
##  <a name="createinstance"></a>CAnimationVariableIntegerChangeHandler::CreateInstance  
 Crée une instance de rappel CAnimationVariableIntegerChangeHandler.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,  
    IUIAnimationVariableIntegerChangeHandler** ppHandler);
```  
  
### <a name="parameters"></a>Paramètres  
 `pAnimationController`  
 Pointeur vers le contrôleur de l’animation, qui doit recevoir des événements.  
  
 `ppHandler`  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne S_OK. Sinon, elle retourne un code d’erreur HRESULT.  
  
##  <a name="onintegervaluechanged"></a>CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged  
 Appelé lorsqu’une valeur d’une variable d’animation a changé.  
  
```  
IFACEMETHOD(OnIntegerValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in INT32 newValue,
    __in INT32 previousValue);
```  
  
### <a name="parameters"></a>Paramètres  
 `storyboard`  
 La table de montage séquentiel qui anime la variable.  
  
 `variable`  
 La variable d’animation qui a été mis à jour.  
  
 `newValue`  
 La nouvelle valeur arrondie.  
  
 `previousValue`  
 La précédente valeur arrondie.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si la méthode réussit ; sinon E_FAIL.  
  
##  <a name="setanimationcontroller"></a>CAnimationVariableIntegerChangeHandler::SetAnimationController  
 Stocke un pointeur vers le contrôleur de l’animation pour acheminer les événements.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>Paramètres  
 `pAnimationController`  
 Pointeur vers le contrôleur de l’animation, qui doit recevoir des événements.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)
