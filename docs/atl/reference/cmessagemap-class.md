---
title: Classe de CMessageMap | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMessageMap
- ATL.CMessageMap
- ATL::CMessageMap
dev_langs:
- C++
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f0b40c73101463b934e3fcf299171bea142fe838
ms.lasthandoff: 02/24/2017

---
# <a name="cmessagemap-class"></a>CMessageMap (classe)
Cette classe autorise que les messages d’un objet est mappé pour l’accès à un autre objet.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class ATL_NO_VTABLE CMessageMap
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMessageMap::ProcessWindowMessage](#processwindowmessage)|Accède à une table des messages dans la `CMessageMap`-classe dérivée.|  
  
## <a name="remarks"></a>Remarques  
 `CMessageMap`est une classe de base abstraite qui laisse les messages d’un objet est mappé pour être accessible par un autre objet. Dans l’ordre pour un objet d’exposer ses tables des messages, sa classe doit dériver de `CMessageMap`.  
  
 ATL utilise `CMessageMap` pour les contenus de support de windows et le chaînage de carte dynamique des messages. Par exemple, toute classe qui contient un [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) objet doit dériver de `CMessageMap`. Le code suivant provient de la [SUBEDIT](../../visual-cpp-samples.md) exemple. Via [CComControl](../../atl/reference/ccomcontrol-class.md), le `CAtlEdit` classe dérive automatiquement `CMessageMap`.  
  
 [!code-cpp[NVC_ATL_Windowing&#90;](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]  
  
 Étant donné que la fenêtre de relation contenant-contenue, `m_EditCtrl`, utilise une table des messages dans la classe de conteneur, `CAtlEdit` dérive de `CMessageMap`.  
  
 Pour plus d’informations sur les tables des messages, consultez [tables des messages](../../atl/message-maps-atl.md) dans l’article « Classes de fenêtre ATL ».  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
  
##  <a name="a-nameprocesswindowmessagea--cmessagemapprocesswindowmessage"></a><a name="processwindowmessage"></a>CMessageMap::ProcessWindowMessage  
 Accède à la table des messages identifiée par `dwMsgMapID` dans un `CMessageMap`-classe dérivée.  
  
```
virtual BOOL ProcessWindowMessage(  
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult,
    DWORD dwMsgMapID) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `hWnd`  
 [in] Handle de la fenêtre de réception du message.  
  
 `uMsg`  
 [in] Le message est envoyé à la fenêtre.  
  
 `wParam`  
 [in] Spécifique au message des informations supplémentaires.  
  
 `lParam`  
 [in] Spécifique au message des informations supplémentaires.  
  
 `lResult`  
 [out] Le résultat du traitement du message.  
  
 `dwMsgMapID`  
 [in] Identificateur de la table des messages qui traitera le message. La table des messages par défaut déclaré avec [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554), est identifiée par 0. Une table des messages secondaire, déclarée avec [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), est identifié par `msgMapID`.  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si le message est entièrement gérée ; sinon, **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Appelée par la procédure de fenêtre un [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) de l’objet ou d’un objet qui est dynamiquement chaînage à la table des messages.  
  
## <a name="see-also"></a>Voir aussi  
 [CDynamicChain (classe)](../../atl/reference/cdynamicchain-class.md)   
 [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [ALT_MSG_MAP](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

