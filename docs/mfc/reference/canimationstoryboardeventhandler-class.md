---
title: CAnimationStoryboardEventHandler, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationStoryboardEventHandler [MFC], CAnimationStoryboardEventHandler
- CAnimationStoryboardEventHandler [MFC], CreateInstance
- CAnimationStoryboardEventHandler [MFC], OnStoryboardStatusChanged
- CAnimationStoryboardEventHandler [MFC], OnStoryboardUpdated
- CAnimationStoryboardEventHandler [MFC], SetAnimationController
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 242d9a1de478b4fe5c9bc80a7c77aa0148efbe24
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="canimationstoryboardeventhandler-class"></a>CAnimationStoryboardEventHandler, classe
Implémente un rappel, qui est appelé par l'API d'animation lorsque l'état d'un storyboard est modifié ou qu'un storyboard est mis à jour.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler](#canimationstoryboardeventhandler)|Construit un objet `CAnimationStoryboardEventHandler`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimationStoryboardEventHandler::CreateInstance](#createinstance)|Crée une instance de `CAnimationStoryboardEventHandler` rappel.|  
|[CAnimationStoryboardEventHandler::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Gère les `OnStoryboardStatusChanged` les événements qui se produisent lorsque l’état d’un storyboard (remplace `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged`.)|  
|[CAnimationStoryboardEventHandler::OnStoryboardUpdated](#onstoryboardupdated)|Gère les `OnStoryboardUpdated` les événements qui se produisent lorsqu’un storyboard est mis à jour (remplace `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated`.)|  
|[CAnimationStoryboardEventHandler::SetAnimationController](#setanimationcontroller)|Stocke un pointeur vers le contrôleur de l’animation pour acheminer les événements.|  
  
## <a name="remarks"></a>Remarques  
 Ce gestionnaire d’événements est créé et passé à `IUIAnimationStoryboard::SetStoryboardEventHandler` méthode, lorsque vous appelez `CAnimationController::EnableStoryboardEventHandler`.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationStoryboardEventHandlerBase`  
  
 `CAnimationStoryboardEventHandler`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxanimationcontroller.h  
  
##  <a name="canimationstoryboardeventhandler"></a>CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler  
 Construit un objet CAnimationStoryboardEventHandler.  
  
```  
CAnimationStoryboardEventHandler();
```  
  
##  <a name="createinstance"></a>CAnimationStoryboardEventHandler::CreateInstance  
 Crée une instance de rappel CAnimationStoryboardEventHandler.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,  
    IUIAnimationStoryboardEventHandler** ppHandler);
```  
  
### <a name="parameters"></a>Paramètres  
 `pAnimationController`  
 Pointeur vers le contrôleur de l’animation, qui doit recevoir des événements.  
  
 `ppHandler`  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne S_OK. Sinon, elle retourne un code d’erreur HRESULT.  
  
##  <a name="onstoryboardstatuschanged"></a>CAnimationStoryboardEventHandler::OnStoryboardStatusChanged  
 Gère les événements OnStoryboardStatusChanged qui se produisent lorsque l’état d’un storyboard  
  
```  
IFACEMETHOD(OnStoryboardStatusChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in UI_ANIMATION_STORYBOARD_STATUS newStatus,
    __in UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```  
  
### <a name="parameters"></a>Paramètres  
 `storyboard`  
 Pointeur vers la table de montage séquentiel dont l’état a changé.  
  
 `newStatus`  
 Spécifie le nouvel état de la table de montage séquentiel.  
  
 `previousStatus`  
 Spécifie l’état précédent de la table de montage séquentiel.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si la méthode réussit ; sinon E_FAIL.  
  
##  <a name="onstoryboardupdated"></a>CAnimationStoryboardEventHandler::OnStoryboardUpdated  
 Gère les événements OnStoryboardUpdated qui se produisent lorsqu’un storyboard est mis à jour.  
  
```  
IFACEMETHOD(OnStoryboardUpdated) (__in IUIAnimationStoryboard* storyboard);
```  
  
### <a name="parameters"></a>Paramètres  
 `storyboard`  
 Pointeur vers le storyboard qui a été mis à jour.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si la méthode réussit ; sinon E_FAIL.  
  
##  <a name="setanimationcontroller"></a>CAnimationStoryboardEventHandler::SetAnimationController  
 Stocke un pointeur vers le contrôleur de l’animation pour acheminer les événements.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>Paramètres  
 `pAnimationController`  
 Pointeur vers le contrôleur de l’animation, qui doit recevoir des événements.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

