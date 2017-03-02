---
title: Classe de CDynamicChain | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CDynamicChain
- ATL.CDynamicChain
- CDynamicChain
dev_langs:
- C++
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
caps.latest.revision: 21
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
ms.openlocfilehash: 4da97d0b3d72400d7e285fde187e6860759900af
ms.lasthandoff: 02/24/2017

---
# <a name="cdynamicchain-class"></a>CDynamicChain (classe)
Cette classe fournit des méthodes prenant en charge le chaînage dynamique des tables des messages.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CDynamicChain
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDynamicChain::CDynamicChain](#cdynamicchain)|Constructeur.|  
|[CDynamicChain :: ~ CDynamicChain](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDynamicChain::CallChain](#callchain)|Indique un message Windows à la table des messages d’un autre objet.|  
|[CDynamicChain::RemoveChainEntry](#removechainentry)|Supprime une entrée de mappage de message de la collection.|  
|[CDynamicChain::SetChainEntry](#setchainentry)|Ajoute une entrée de mappage de messages à la collection ou modifie une entrée existante.|  
  
## <a name="remarks"></a>Remarques  
 `CDynamicChain`gère une collection de tables des messages, l’activation d’un message d’être acheminés au moment de l’exécution à la table des messages d’un autre objet.  
  
 Pour prendre en charge le chaînage dynamique des tables des messages, procédez comme suit :  
  
-   Dérivez votre classe de `CDynamicChain`. Dans la table des messages, spécifiez la [macro CHAIN_MSG_MAP_DYNAMIC](http://msdn.microsoft.com/library/7e5c72b7-cb31-4f3b-8a1b-6293804af220) macro pour la chaîne de la table des messages par défaut d’un autre objet.  
  
-   Dériver de chaque classe que vous souhaitez pour la chaîne [CMessageMap](../../atl/reference/cmessagemap-class.md). `CMessageMap`permet à un objet d’exposer ses tables des messages à d’autres objets.  
  
-   Appelez `CDynamicChain::SetChainEntry` pour identifier l’objet et mapper les messages vous souhaitez chaîne.  
  
 Par exemple, supposons que votre classe est définie comme suit :  
  
 [!code-cpp[NVC_ATL_Windowing&#88;](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]  
  
 Le client appelle ensuite `CMyWindow::SetChainEntry`:  
  
 [!code-cpp[NVC_ATL_Windowing&#89;](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]  
  
 où `chainedObj` est l’objet de chaîne et est une instance d’une classe dérivée de `CMessageMap`. Maintenant, si `myCtl` reçoit un message qui n’est pas géré par `OnPaint` ou `OnSetFocus`, la procédure de fenêtre achemine le message vers `chainedObj`de table des messages par défaut.  
  
 Pour plus d’informations sur le chaînage de mappage de message, consultez [les tables des messages](../../atl/message-maps-atl.md) dans l’article « Classes de fenêtre ATL ».  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
  
##  <a name="a-namecallchaina--cdynamicchaincallchain"></a><a name="callchain"></a>CDynamicChain::CallChain  
 Dirige le message Windows à la table des messages d’un autre objet.  
  
```
BOOL CallChain(  
    DWORD dwChainID,
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwChainID`  
 [in] Identificateur unique associé à l’objet chaînée et sa table des messages.  
  
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
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si le message est entièrement traité ; sinon, **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Pour appeler la procédure de fenêtre `CallChain`, vous devez spécifier le [macro CHAIN_MSG_MAP_DYNAMIC](http://msdn.microsoft.com/library/7e5c72b7-cb31-4f3b-8a1b-6293804af220) macro dans votre table des messages. Pour obtenir un exemple, consultez la [CDynamicChain](../../atl/reference/cdynamicchain-class.md) vue d’ensemble.  
  
 `CallChain`nécessite un appel précédent à [SetChainEntry](#setchainentry) pour associer la `dwChainID` valeur avec un objet et sa table des messages.  
  
##  <a name="a-namecdynamicchaina--cdynamicchaincdynamicchain"></a><a name="cdynamicchain"></a>CDynamicChain::CDynamicChain  
 Constructeur.  
  
```
CDynamicChain();
```  
  
##  <a name="a-namedtora--cdynamicchaincdynamicchain"></a><a name="dtor"></a>CDynamicChain :: ~ CDynamicChain  
 Destructeur.  
  
```
~CDynamicChain();
```  
  
### <a name="remarks"></a>Remarques  
 Libère toutes les ressources attribuées.  
  
##  <a name="a-nameremovechainentrya--cdynamicchainremovechainentry"></a><a name="removechainentry"></a>CDynamicChain::RemoveChainEntry  
 Supprime la table des messages spécifié de la collection.  
  
```
BOOL RemoveChainEntry(DWORD dwChainID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwChainID`  
 [in] Identificateur unique associé à l’objet chaînée et sa table des messages. Vous définissez initialement cette valeur via un appel à [SetChainEntry](#setchainentry).  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si la table des messages a été supprimée de la collection. Dans le cas contraire, **FALSE**.  
  
##  <a name="a-namesetchainentrya--cdynamicchainsetchainentry"></a><a name="setchainentry"></a>CDynamicChain::SetChainEntry  
 Ajoute la table des messages spécifié à la collection.  
  
```
BOOL SetChainEntry(  
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwChainID`  
 [in] Identificateur unique associé à l’objet chaînée et sa table des messages.  
  
 `pObject`  
 [in] Pointeur vers l’objet chaînée déclarant de la table des messages. Cet objet doit dériver de [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Identificateur de la table des messages dans l’objet chaînée. La valeur par défaut est 0, qui identifie la table des messages par défaut déclarée avec [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554). Pour spécifier une autre table des messages déclarée avec [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), transmettez `msgMapID`.  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si la table des messages est correctement ajoutée à la collection. Dans le cas contraire, **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Si le `dwChainID` valeur existe déjà dans la collection, son objet associé et la table des messages sont remplacés par `pObject` et `dwMsgMapID`, respectivement. Sinon, une nouvelle entrée est ajoutée.  
  
## <a name="see-also"></a>Voir aussi  
 [CWindowImpl (classe)](../../atl/reference/cwindowimpl-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

