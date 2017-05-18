---
title: Message de Macros de mappage (ATL) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 8097982d6574af2ce1ba592dbead8abf6f6433df
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="message-map-macros-atl"></a>Macros de mappage des messages (ATL)
Ces macros définissent les tables des messages et des entrées.  
  
|||  
|-|-|  
|[ALT_MSG_MAP](#alt_msg_map)|Marque le début d’une autre table des messages.|  
|[BEGIN_MSG_MAP](#begin_msg_map)|Marque le début de la table des messages par défaut.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Est lié à une autre table des messages dans la classe de base.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Est lié à une autre table des messages dans un membre de données de la classe.|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Est lié à la table des messages par défaut dans la classe de base.|  
|[MACRO CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Est lié à la table des messages dans une autre classe au moment de l’exécution.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Est lié à la table des messages par défaut dans un membre de données de la classe.|  
|[COMMAND_CODE_HANDLER](#command_code_handler)|Mappe un **WM_COMMAND** message à une fonction de gestionnaire, selon le code de notification.|  
|[COMMAND_HANDLER](#command_handler)|Mappe un **WM_COMMAND** message à une fonction de gestionnaire, selon le code de notification et l’identificateur de l’élément de menu, le contrôle ou l’accélérateur.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|Mappe un **WM_COMMAND** message à une fonction de gestionnaire, basée sur l’identificateur de l’élément de menu, le contrôle ou l’accélérateur.|  
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|Mappe un **WM_COMMAND** message à une fonction de gestionnaire, selon le code de notification et une plage contiguë d’identificateurs de contrôle.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Mappe un **WM_COMMAND** message à une fonction de gestionnaire, selon une plage contiguë d’identificateurs de contrôle.|  
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|Implémente une table des messages vide.|  
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|Fournit un gestionnaire par défaut pour les messages réfléchis ne sont pas gérées dans le cas contraire.|  
|[END_MSG_MAP](#end_msg_map)|Marque la fin d’une table des messages.|  
|[FORWARD_NOTIFICATIONS](#forward_notifications)|Envoie des messages de notification de la fenêtre parente.|  
|[MESSAGE_HANDLER](#message_handler)|Mappe un message Windows à une fonction gestionnaire.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Mappe une plage contiguë de Windows aux messages à une fonction gestionnaire.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Mappe un **WM_NOTIFY** message à une fonction de gestionnaire, selon le code de notification.|  
|[NOTIFY_HANDLER](#notify_handler)|Mappe un **WM_NOTIFY** message à une fonction de gestionnaire, selon le code de notification et l’identificateur du contrôle.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Mappe un **WM_NOTIFY** message à une fonction de gestionnaire, selon l’identificateur du contrôle.|  
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|Mappe un **WM_NOTIFY** message à une fonction de gestionnaire, selon le code de notification et une plage contiguë d’identificateurs de contrôle.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Mappe un **WM_NOTIFY** message à une fonction de gestionnaire, selon une plage contiguë d’identificateurs de contrôle.|  
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|Reflète les messages de notification à la fenêtre qui les a envoyés.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Mappe un réfléchi **WM_COMMAND** message à une fonction de gestionnaire, selon le code de notification.|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Mappe un réfléchi **WM_COMMAND** message à une fonction de gestionnaire, selon le code de notification et l’identificateur de l’élément de menu, le contrôle ou l’accélérateur.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Mappe un réfléchi **WM_COMMAND** message à une fonction de gestionnaire, basée sur l’identificateur de l’élément de menu, le contrôle ou l’accélérateur.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Mappe un réfléchi **WM_COMMAND** message à une fonction de gestionnaire, selon le code de notification et une plage contiguë d’identificateurs de contrôle.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Mappe un réfléchi **WM_COMMAND** message à une fonction de gestionnaire, selon une plage contiguë d’identificateurs de contrôle.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Mappe un réfléchi **WM_NOTIFY** message à une fonction de gestionnaire, selon le code de notification.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Mappe un réfléchi **WM_NOTIFY** message à une fonction de gestionnaire, selon le code de notification et l’identificateur du contrôle.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Mappe un réfléchi **WM_NOTIFY** message à une fonction de gestionnaire, selon l’identificateur du contrôle.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Mappe un réfléchi **WM_NOTIFY** message à une fonction de gestionnaire, selon le code de notification et une plage contiguë d’identificateurs de contrôle.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Mappe un réfléchi **WM_NOTIFY** message à une fonction de gestionnaire, selon une plage contiguë d’identificateurs de contrôle.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  

##  <a name="alt_msg_map"></a>ALT_MSG_MAP  
 Marque le début d’une autre table des messages.  
  
```
ALT_MSG_MAP(msgMapID)
```  
  
### <a name="parameters"></a>Paramètres  
 `msgMapID`  
 [in] Identificateur de la carte de message.  
  
### <a name="remarks"></a>Remarques  
 ATL identifie chaque mappage de message par un nombre. La table des messages par défaut (déclaré avec le `BEGIN_MSG_MAP` macro) est identifié par 0. Une autre table des messages est identifiée par `msgMapID`.  
  
 Tables des messages sont utilisés pour traiter les messages envoyés à une fenêtre. Par exemple, [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) vous permet de spécifier l’identificateur d’une table des messages dans l’objet conteneur. [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc) utilise ensuite cette table des messages pour diriger les messages de la fenêtre de relation contenant-contenu à la fonction gestionnaire appropriée ou à une autre table des messages. Pour obtenir la liste des macros qui déclarent des fonctions du gestionnaire, voir [BEGIN_MSG_MAP](#begin_msg_map).  
  
 Toujours commencer avec une table des messages `BEGIN_MSG_MAP`. Vous pouvez ensuite déclarer les tables des messages de remplacement suivants.  
  
 Le [END_MSG_MAP](#end_msg_map) macro marque la fin de la table des messages. Notez qu’il existe toujours exactement une instance de `BEGIN_MSG_MAP` et `END_MSG_MAP`.  
  
 Pour plus d’informations sur l’utilisation des tables des messages dans ATL, consultez [tables des messages](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre le mappage de message par défaut et une autre table des messages, chacun contenant une fonction de gestionnaire :  
  
 [!code-cpp[NVC_ATL_Windowing&#98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 L’exemple suivant montre deux tables des messages de remplacement. La table des messages par défaut est vide.  
  
 [!code-cpp[NVC_ATL_Windowing&#99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   

##  <a name="begin_msg_map"></a>BEGIN_MSG_MAP  
 Marque le début de la table des messages par défaut.  
  
```
BEGIN_MSG_MAP(theClass)
```  
  
### <a name="parameters"></a>Paramètres  
 `theClass`  
 [in] Le nom de la classe contenant la table des messages.  
  
### <a name="remarks"></a>Remarques  
 [CWindowImpl::WindowProc](cwindowimpl-class.md#windowproc) utilise la table des messages par défaut pour traiter les messages envoyés à la fenêtre. La table des messages dirige les messages à la fonction gestionnaire approprié ou à une autre table des messages.  

  
 Les macros suivantes mappent un message à une fonction gestionnaire. Cette fonction doit être définie dans `theClass`.  
  
|Macro|Description|  
|-----------|-----------------|  
|[MESSAGE_HANDLER](#message_handler)|Mappe un message Windows à une fonction gestionnaire.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Mappe une plage contiguë de Windows aux messages à une fonction gestionnaire.|  
|[COMMAND_HANDLER](#command_handler)|Mappe un **WM_COMMAND** message à une fonction de gestionnaire, selon le code de notification et l’identificateur de l’élément de menu, le contrôle ou l’accélérateur.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|Mappe un **WM_COMMAND** message à une fonction de gestionnaire, basée sur l’identificateur de l’élément de menu, le contrôle ou l’accélérateur.|  
|[COMMAND_CODE_HANDLER](#command_handler)|Mappe un **WM_COMMAND** message à une fonction de gestionnaire, selon le code de notification.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Mappe une plage contiguë de **WM_COMMAND** messages à une fonction gestionnaire, en fonction de l’identificateur de l’élément de menu, le contrôle ou l’accélérateur.|  
|[NOTIFY_HANDLER](#notify_handler)|Mappe un **WM_NOTIFY** message à une fonction de gestionnaire, selon le code de notification et l’identificateur du contrôle.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Mappe un **WM_NOTIFY** message à une fonction de gestionnaire, selon l’identificateur du contrôle.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Mappe un **WM_NOTIFY** message à une fonction de gestionnaire, selon le code de notification.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Mappe une plage contiguë de **WM_NOTIFY** messages à une fonction gestionnaire, selon l’identificateur du contrôle.|  
  
 Les macros suivantes dirigent les messages vers une autre table des messages. Ce processus est appelé « chaînage ».  
  
|Macro|Description|  
|-----------|-----------------|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Est lié à la table des messages par défaut dans la classe de base.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Est lié à la table des messages par défaut dans un membre de données de la classe.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Est lié à une autre table des messages dans la classe de base.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Est lié à une autre table des messages dans un membre de données de la classe.|  
|[MACRO CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Est lié à la table des messages par défaut dans une autre classe au moment de l’exécution.|  
  
 Les macros suivantes dirigent « reflétées » des messages à partir de la fenêtre parente. Par exemple, un contrôle normalement envoie des messages de notification à sa fenêtre parente pour traitement, mais la fenêtre parente peut refléter le message au contrôle.  
  
|Macro|Description|  
|-----------|-----------------|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Mappe un réfléchi **WM_COMMAND** message à une fonction de gestionnaire, selon le code de notification et l’identificateur de l’élément de menu, le contrôle ou l’accélérateur.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Mappe un réfléchi **WM_COMMAND** message à une fonction de gestionnaire, basée sur l’identificateur de l’élément de menu, le contrôle ou l’accélérateur.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Mappe un réfléchi **WM_COMMAND** message à une fonction de gestionnaire, selon le code de notification.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Mappe un réfléchi **WM_COMMAND** message à une fonction de gestionnaire, selon une plage contiguë d’identificateurs de contrôle.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Mappe un réfléchi **WM_COMMAND** message à une fonction de gestionnaire, selon le code de notification et une plage contiguë d’identificateurs de contrôle.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Mappe un réfléchi **WM_NOTIFY** message à une fonction de gestionnaire, selon le code de notification et l’identificateur du contrôle.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Mappe un réfléchi **WM_NOTIFY** message à une fonction de gestionnaire, selon l’identificateur du contrôle.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Mappe un réfléchi **WM_NOTIFY** message à une fonction de gestionnaire, selon le code de notification.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Mappe un réfléchi **WM_NOTIFY** message à une fonction de gestionnaire, selon une plage contiguë d’identificateurs de contrôle.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Mappe un réfléchi **WM_NOTIFY** message à une fonction de gestionnaire, selon le code de notification et une plage contiguë d’identificateurs de contrôle.|  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#102;](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]  
  
 Lorsqu’un `CMyExtWindow` objet reçoit un `WM_PAINT` message, le message est dirigé vers `CMyExtWindow::OnPaint` pour le traitement. Si `OnPaint` indique le message nécessite un traitement supplémentaire, le message est ensuite dirigé vers la table des messages par défaut dans `CMyBaseWindow`.  
  
 En plus de la table des messages par défaut, vous pouvez définir une autre table des messages avec [ALT_MSG_MAP](#alt_msg_map). Toujours commencer avec une table des messages `BEGIN_MSG_MAP`. Vous pouvez ensuite déclarer les tables des messages de remplacement suivants. L’exemple suivant montre le mappage de message par défaut et une autre table des messages, chacun contenant une fonction de gestionnaire :  
  
 [!code-cpp[NVC_ATL_Windowing&#98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 L’exemple suivant montre deux tables des messages de remplacement. La table des messages par défaut est vide.  
  
 [!code-cpp[NVC_ATL_Windowing&#99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
 Le [END_MSG_MAP](#end_msg_map) macro marque la fin de la table des messages. Notez qu’il existe toujours exactement une instance de `BEGIN_MSG_MAP` et `END_MSG_MAP`.  
  
 Pour plus d’informations sur l’utilisation des tables des messages dans ATL, consultez [tables des messages](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="chain_msg_map_alt"></a>CHAIN_MSG_MAP_ALT  
 Définit une entrée dans une table des messages.  
  
```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```  
  
### <a name="parameters"></a>Paramètres  
 `theChainClass`  
 [in] Le nom de la classe de base qui contient la table des messages.  
  
 `msgMapID`  
 [in] Identificateur de la carte de message.  
  
### <a name="remarks"></a>Notes  
 `CHAIN_MSG_MAP_ALT`dirige les messages vers une autre table des messages dans une classe de base. Vous avez devez déclaré cette autre table des messages avec [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Pour diriger les messages vers la table des messages par défaut d’une classe de base (déclaré avec [BEGIN_MSG_MAP](#begin_msg_map)), utilisez `CHAIN_MSG_MAP`. Pour obtenir un exemple, consultez [CHAIN_MSG_MAP](#chain_msg_map).  
  
> [!NOTE]
>  Toujours commencer avec une table des messages `BEGIN_MSG_MAP`. Vous pouvez ensuite déclarer les tables des messages de remplacement suivants avec `ALT_MSG_MAP`. Le [END_MSG_MAP](#end_msg_map) macro marque la fin de la table des messages. Chaque message doit avoir exactement une instance de `BEGIN_MSG_MAP` et `END_MSG_MAP`.  
  
 Pour plus d’informations sur l’utilisation des tables des messages dans ATL, consultez [tables des messages](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="chain_msg_map_alt_member"></a>CHAIN_MSG_MAP_ALT_MEMBER  
 Définit une entrée dans une table des messages.  
  
```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```  
  
### <a name="parameters"></a>Paramètres  
 `theChainMember`  
 [in] Le nom du membre de données contenant la table des messages.  
  
 `msgMapID`  
 [in] Identificateur de la carte de message.  
  
### <a name="remarks"></a>Notes  
 `CHAIN_MSG_MAP_ALT_MEMBER`dirige les messages vers une autre table des messages dans un membre de données. Vous avez devez déclaré cette autre table des messages avec [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Pour diriger les messages vers la table des messages d’un membre de données par défaut (déclaré avec [BEGIN_MSG_MAP](#begin_msg_map)), utilisez `CHAIN_MSG_MAP_MEMBER`. Pour obtenir un exemple, consultez [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member).  
  
> [!NOTE]
>  Toujours commencer avec une table des messages `BEGIN_MSG_MAP`. Vous pouvez ensuite déclarer les tables des messages de remplacement suivants avec `ALT_MSG_MAP`. Le [END_MSG_MAP](#end_msg_map) macro marque la fin de la table des messages. Chaque message doit avoir exactement une instance de `BEGIN_MSG_MAP` et `END_MSG_MAP`.  
  
 Pour plus d’informations sur l’utilisation des tables des messages dans ATL, consultez [tables des messages](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="chain_msg_map"></a>CHAIN_MSG_MAP  
 Définit une entrée dans une table des messages.  
  
```
CHAIN_MSG_MAP(theChainClass)
```  
  
### <a name="parameters"></a>Paramètres  
 `theChainClass`  
 [in] Le nom de la classe de base qui contient la table des messages.  
  
### <a name="remarks"></a>Notes  
 `CHAIN_MSG_MAP`dirige les messages vers la table des messages par défaut d’une classe de base (déclaré avec [BEGIN_MSG_MAP](#begin_msg_map)). Pour diriger les messages vers la table des messages secondaire d’une classe de base (déclaré avec [ALT_MSG_MAP](#alt_msg_map)), utilisez [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt).  
  
> [!NOTE]
>  Toujours commencer avec une table des messages `BEGIN_MSG_MAP`. Vous pouvez ensuite déclarer les tables des messages de remplacement suivants avec `ALT_MSG_MAP`. Le [END_MSG_MAP](#end_msg_map) macro marque la fin de la table des messages. Chaque message doit avoir exactement une instance de `BEGIN_MSG_MAP` et `END_MSG_MAP`.  
  
 Pour plus d’informations sur l’utilisation des tables des messages dans ATL, consultez [tables des messages](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#107;](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]  
  
 Cet exemple illustre les points suivants :  
  
-   Si une procédure de fenêtre utilise `CMyClass`de table des messages par défaut et `OnPaint` ne pas handle d’un message, le message est dirigé vers `CMyBaseClass`de table des messages par défaut pour le traitement.  
  
-   Si une procédure de fenêtre à l’aide de la première table des messages secondaire dans `CMyClass`, tous les messages sont dirigés vers `CMyBaseClass`de table des messages par défaut.  
  
-   Si une procédure de fenêtre utilise `CMyClass`du deuxième message autre mapper et `OnChar` ne pas handle d’un message, le message est dirigé vers la table des messages de remplacement spécifié dans `CMyBaseClass`. `CMyBaseClass`doit avoir déclaré cette table des messages avec `ALT_MSG_MAP(1)`.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="chain_msg_map_dynamic"></a>MACRO CHAIN_MSG_MAP_DYNAMIC  
 Définit une entrée dans une table des messages.  
  
```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```  
  
### <a name="parameters"></a>Paramètres  
 *dynaChainID*  
 [in] Identificateur unique de la table des messages d’un objet.  
  
### <a name="remarks"></a>Notes  
 `CHAIN_MSG_MAP_DYNAMIC`Indique les messages, au moment de l’exécution à la table des messages par défaut dans un autre objet. L’objet et sa table des messages sont associés *dynaChainID*, que vous définissez via [CDynamicChain::SetChainEntry](cdynamicchain-class.md#setchainentry). Vous devez dériver votre classe de `CDynamicChain` afin d’utiliser `CHAIN_MSG_MAP_DYNAMIC`. Pour obtenir un exemple, consultez la [CDynamicChain](../../atl/reference/cdynamicchain-class.md) vue d’ensemble.  

  
> [!NOTE]
>  Toujours commencer avec une table des messages [BEGIN_MSG_MAP](#begin_msg_map). Vous pouvez ensuite déclarer les tables des messages de remplacement suivants avec `ALT_MSG_MAP`. Le [END_MSG_MAP](#end_msg_map) macro marque la fin de la table des messages. Chaque message doit avoir exactement une instance de `BEGIN_MSG_MAP` et `END_MSG_MAP`.  
  
 Pour plus d’informations sur l’utilisation des tables des messages dans ATL, consultez [tables des messages](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="chain_msg_map_member"></a>CHAIN_MSG_MAP_MEMBER  
 Définit une entrée dans une table des messages.  
  
```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```  
  
### <a name="parameters"></a>Paramètres  
 `theChainMember`  
 [in] Le nom du membre de données contenant la table des messages.  
  
### <a name="remarks"></a>Remarques  
 `CHAIN_MSG_MAP_MEMBER`dirige les messages vers la table des messages par défaut d’un membre de données (déclaré avec [BEGIN_MSG_MAP](#begin_msg_map)). Pour diriger les messages vers la table des messages secondaire d’un membre de données (déclaré avec [ALT_MSG_MAP](#alt_msg_map)), utilisez [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member).  
  
> [!NOTE]
>  Toujours commencer avec une table des messages `BEGIN_MSG_MAP`. Vous pouvez ensuite déclarer les tables des messages de remplacement suivants avec `ALT_MSG_MAP`. Le [END_MSG_MAP](#end_msg_map) macro marque la fin de la table des messages. Chaque message doit avoir exactement une instance de `BEGIN_MSG_MAP` et `END_MSG_MAP`.  
  
 Pour plus d’informations sur l’utilisation des tables des messages dans ATL, consultez [tables des messages](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#108;](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]  
  
 Cet exemple illustre les points suivants :  
  
-   Si une procédure de fenêtre utilise `CMyClass`de table des messages par défaut et `OnPaint` ne pas handle d’un message, le message est dirigé vers `m_obj`de table des messages par défaut pour le traitement.  
  
-   Si une procédure de fenêtre à l’aide de la première table des messages secondaire dans `CMyClass`, tous les messages sont dirigés vers `m_obj`de table des messages par défaut.  
  
-   Si une procédure de fenêtre utilise `CMyClass`du deuxième message autre mapper et `OnChar` ne pas handle d’un message, le message est dirigé vers la table des messages de remplacement spécifié de `m_obj`. Classe `CMyContainedClass` est déclarée avec cette table des messages `ALT_MSG_MAP(1)`.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="command_code_handler"></a>COMMAND_CODE_HANDLER  
 Semblable à [COMMAND_HANDLER](#command_handler), mais mappe un [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) message basé uniquement sur le code de notification.  
  
```
COMMAND_CODE_HANDLER(code, func)
```  
  
### <a name="parameters"></a>Paramètres  
 `code`  
 [in] Le code de notification.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="command_handler"></a>COMMAND_HANDLER  
 Définit une entrée dans une table des messages.  
  
```
COMMAND_HANDLER(id, code, func)
```    
  
### <a name="parameters"></a>Paramètres  
 `id`  
 [in] Identificateur de l’élément de menu, le contrôle ou l’accélérateur.  
  
 `code`  
 [in] Le code de notification.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  
  
### <a name="remarks"></a>Remarques  
 `COMMAND_HANDLER`mappe un [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) message à la fonction gestionnaire spécifié, en fonction du code de notification et l’identificateur du contrôle. Exemple :  
  
 [!code-cpp[NVC_ATL_Windowing&#119;](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]  
  
 Toute fonction spécifiée dans un `COMMAND_HANDLER` macro doit être définie comme suit :  
  
 `LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`  
  
 Les jeux de cartes message `bHandled` à **TRUE** avant `CommandHandler` est appelée. Si `CommandHandler` ne gère pas entièrement le message, il doit définir `bHandled` à **FALSE** pour indiquer que le message nécessite un traitement supplémentaire.  
  
> [!NOTE]
>  Toujours commencer avec une table des messages [BEGIN_MSG_MAP](#begin_msg_map). Vous pouvez ensuite déclarer les tables des messages de remplacement suivants avec [ALT_MSG_MAP](#alt_msg_map). Le [END_MSG_MAP](#end_msg_map) macro marque la fin de la table des messages. Chaque message doit avoir exactement une instance de `BEGIN_MSG_MAP` et `END_MSG_MAP`.  
  
 En plus de `COMMAND_HANDLER`, vous pouvez utiliser [MESSAGE_HANDLER](#message_handler) pour mapper un **WM_COMMAND** message sans tenir compte d’un identificateur ou le code. Dans ce cas, `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)` dirige toutes **WM_COMMAND** des messages à `OnHandlerFunction`.  
  
 Pour plus d’informations sur l’utilisation des tables des messages dans ATL, consultez [tables des messages](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="command_id_handler"></a>COMMAND_ID_HANDLER  
 Semblable à [COMMAND_HANDLER](#command_handler), mais mappe un [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) basé sur des messages uniquement sur l’identificateur de l’élément de menu, le contrôle ou l’accélérateur.  
  
```
COMMAND_ID_HANDLER(id, func)
```  
  
### <a name="parameters"></a>Paramètres  
 `id`  
 [in] Identificateur de l’élément de menu, le contrôle ou l’accélérateur de l’envoi du message.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="command_range_code_handler"></a>COMMAND_RANGE_CODE_HANDLER  
 Semblable à [COMMAND_RANGE_HANDLER](#command_range_handler), mais mappe [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) messages avec un code de notification spécifique dans une plage de contrôles à une seule fonction gestionnaire.  
  
```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```    
  
### <a name="parameters"></a>Paramètres  
 `idFirst`  
 [in] Marque le début d’une plage contiguë d’identificateurs de contrôle.  
  
 `idLast`  
 [in] Marque la fin d’une plage contiguë d’identificateurs de contrôle.  
  
 `code`  
 [in] Le code de notification.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  
  
### <a name="remarks"></a>Notes  
 Cette plage est basée sur l’identificateur de l’élément de menu, le contrôle ou l’accélérateur de l’envoi du message.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="command_range_handler"></a>COMMAND_RANGE_HANDLER  
 Semblable à [COMMAND_HANDLER](#command_handler), mais mappe [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) messages à partir d’une plage de contrôles à une seule fonction gestionnaire.  
  
```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```    
  
### <a name="parameters"></a>Paramètres  
 `idFirst`  
 [in] Marque le début d’une plage contiguë d’identificateurs de contrôle.  
  
 `idLast`  
 [in] Marque la fin d’une plage contiguë d’identificateurs de contrôle.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  
  
### <a name="remarks"></a>Remarques  
 Cette plage est basée sur l’identificateur de l’élément de menu, le contrôle ou l’accélérateur de l’envoi du message.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="declare_empty_msg_map"></a>DECLARE_EMPTY_MSG_MAP  
 Déclare une table des messages vide.  
  
```
DECLARE_EMPTY_MSG_MAP()
```  
  
### <a name="remarks"></a>Notes  
 `DECLARE_EMPTY_MSG_MAP`est une macro pratique qui appelle les macros [BEGIN_MSG_MAP](#begin_msg_map) et [END_MSG_MAP](#end_msg_map) pour créer une table des messages vide :  
  
 [!code-cpp[NVC_ATL_Windowing&#122;](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]  
  
##  <a name="default_reflection_handler"></a>DEFAULT_REFLECTION_HANDLER  
 Fournit un gestionnaire par défaut pour la fenêtre enfant (contrôle) qui recevra les messages, réfléchis le gestionnaire passe correctement des messages non gérées à `DefWindowProc`.  
  
```
DEFAULT_REFLECTION_HANDLER()
```  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="end_msg_map"></a>END_MSG_MAP  
 Marque la fin d’une table des messages.  
  
```
END_MSG_MAP()
```  
  
### <a name="remarks"></a>Notes  
 Utilisez toujours la [BEGIN_MSG_MAP](#begin_msg_map) macro pour marquer le début d’une table des messages. Utilisez [ALT_MSG_MAP](#alt_msg_map) pour déclarer les tables des messages de remplacement suivants.  
  
 Notez qu’il existe toujours exactement une instance de `BEGIN_MSG_MAP` et `END_MSG_MAP`.  
  
 Pour plus d’informations sur l’utilisation des tables des messages dans ATL, consultez [tables des messages](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre le mappage de message par défaut et une autre table des messages, chacun contenant une fonction de gestionnaire :  
  
 [!code-cpp[NVC_ATL_Windowing&#98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 L’exemple suivant montre deux tables des messages de remplacement. La table des messages par défaut est vide.  
  
 [!code-cpp[NVC_ATL_Windowing&#99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="forward_notifications"></a>FORWARD_NOTIFICATIONS  
 Envoie des messages de notification de la fenêtre parente.  
  
```
FORWARD_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Remarques  
 Spécifiez cette macro en tant que partie de votre table des messages.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="message_handler"></a>MESSAGE_HANDLER  
 Définit une entrée dans une table des messages.  
  
```
MESSAGE_HANDLER( msg, func )
```  
  
### <a name="parameters"></a>Paramètres  
 `msg`  
 [in] Le message Windows.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  
  
### <a name="remarks"></a>Notes  
 `MESSAGE_HANDLER`mappe un message Windows à la fonction gestionnaire spécifié.  
  
 Toute fonction spécifiée dans un `MESSAGE_HANDLER` macro doit être définie comme suit :  
  
 `LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`  
  
 Les jeux de cartes message `bHandled` à **TRUE** avant `MessageHandler` est appelée. Si `MessageHandler` ne gère pas entièrement le message, il doit définir `bHandled` à **FALSE** pour indiquer que le message nécessite un traitement supplémentaire.  
  
> [!NOTE]
>  Toujours commencer avec une table des messages [BEGIN_MSG_MAP](#begin_msg_map). Vous pouvez ensuite déclarer les tables des messages de remplacement suivants avec [ALT_MSG_MAP](#alt_msg_map). Le [END_MSG_MAP](#end_msg_map) macro marque la fin de la table des messages. Chaque message doit avoir exactement une instance de `BEGIN_MSG_MAP` et `END_MSG_MAP`.  
  
 En plus de `MESSAGE_HANDLER`, vous pouvez utiliser [COMMAND_HANDLER](#command_handler) et [NOTIFY_HANDLER](#notify_handler) pour mapper [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) et [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) messages, respectivement.  
  
 Pour plus d’informations sur l’utilisation des tables des messages dans ATL, consultez [tables des messages](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#129;](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="message_range_handler"></a>MESSAGE_RANGE_HANDLER  
 Semblable à [MESSAGE_HANDLER](#message_handler), mais correspond à une plage de Windows des messages à une seule fonction gestionnaire.  
  
```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```  
  
### <a name="parameters"></a>Paramètres  
 *msgFirst*  
 [in] Marque le début d’une plage contiguë de messages.  
  
 *msgLast*  
 [in] Marque la fin d’une plage contiguë de messages.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="notify_code_handler"></a>NOTIFY_CODE_HANDLER  
 Semblable à [NOTIFY_HANDLER](#notify_handler), mais mappe un [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) message basé uniquement sur le code de notification.  
  
```
NOTIFY_CODE_HANDLER(cd, func)
```  
  
### <a name="parameters"></a>Paramètres  
 `cd`  
 [in] Le code de notification.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="notify_handler"></a>NOTIFY_HANDLER  
 Définit une entrée dans une table des messages.  
  
```
NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Paramètres  
 `id`  
 [in] L’identificateur du contrôle qui envoie le message.  
  
 `cd`  
 [in] Le code de notification.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  
  
### <a name="remarks"></a>Remarques  
 `NOTIFY_HANDLER`mappe un [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) message à la fonction gestionnaire spécifié, en fonction du code de notification et l’identificateur du contrôle.  
  
 Toute fonction spécifiée dans un `NOTIFY_HANDLER` macro doit être définie comme suit :  
  
 `LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`  
  
 Les jeux de cartes message `bHandled` à **TRUE** avant `NotifyHandler` est appelée. Si `NotifyHandler` ne gère pas entièrement le message, il doit définir `bHandled` à **FALSE** pour indiquer que le message nécessite un traitement supplémentaire.  
  
> [!NOTE]
>  Toujours commencer avec une table des messages [BEGIN_MSG_MAP](#begin_msg_map). Vous pouvez ensuite déclarer les tables des messages de remplacement suivants avec [ALT_MSG_MAP](#alt_msg_map). Le [END_MSG_MAP](#end_msg_map) macro marque la fin de la table des messages. Chaque message doit avoir exactement une instance de `BEGIN_MSG_MAP` et `END_MSG_MAP`.  
  
 En plus de `NOTIFY_HANDLER`, vous pouvez utiliser [MESSAGE_HANDLER](#message_handler) pour mapper un **WM_NOTIFY** message sans tenir compte d’un identificateur ou le code. Dans ce cas, `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)` dirige toutes **WM_NOTIFY** des messages à `OnHandlerFunction`.  
  
 Pour plus d’informations sur l’utilisation des tables des messages dans ATL, consultez [tables des messages](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#130;](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="notify_id_handler"></a>NOTIFY_ID_HANDLER  
 Semblable à [NOTIFY_HANDLER](#notify_handler), mais mappe un [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) basé sur des messages uniquement sur l’identificateur du contrôle.  
  
```
NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Paramètres  
 `id`  
 [in] L’identificateur du contrôle qui envoie le message.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="notify_range_code_handler"></a>NOTIFY_RANGE_CODE_HANDLER  
 Semblable à [NOTIFY_RANGE_HANDLER](#notify_range_handler), mais mappe [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) messages avec un code de notification spécifique dans une plage de contrôles à une seule fonction gestionnaire.  
  
```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```  
  
### <a name="parameters"></a>Paramètres  
 `idFirst`  
 [in] Marque le début d’une plage contiguë d’identificateurs de contrôle.  
  
 `idLast`  
 [in] Marque la fin d’une plage contiguë d’identificateurs de contrôle.  
  
 `cd`  
 [in] Le code de notification.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  
  
### <a name="remarks"></a>Remarques  
 Cette plage est basée sur l’identificateur du contrôle qui envoie le message.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="notify_range_handler"></a>NOTIFY_RANGE_HANDLER  
 Semblable à [NOTIFY_HANDLER](#notify_handler), mais mappe [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) messages à partir d’une plage de contrôles à une seule fonction gestionnaire.  
  
```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Paramètres  
 `idFirst`  
 [in] Marque le début d’une plage contiguë d’identificateurs de contrôle.  
  
 `idLast`  
 [in] Marque la fin d’une plage contiguë d’identificateurs de contrôle.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  
  
### <a name="remarks"></a>Remarques  
 Cette plage est basée sur l’identificateur du contrôle qui envoie le message.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="reflect_notifications"></a>REFLECT_NOTIFICATIONS  
 Reflète les messages de notification à la fenêtre enfant (contrôle) qui les a envoyés.  
  
```
REFLECT_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Remarques  
 Spécifiez cette macro en tant que partie de la table des messages de la fenêtre parent.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="reflected_command_code_handler"></a>REFLECTED_COMMAND_CODE_HANDLER  
 Semblable à [COMMAND_CODE_HANDLER](#command_code_handler), mais mappe des commandes réfléchies à partir de la fenêtre parente.  
  
```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```  
  
### <a name="parameters"></a>Paramètres  
 `code`  
 [in] Le code de notification.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
   
##  <a name="reflected_command_handler"></a>REFLECTED_COMMAND_HANDLER  
 Semblable à [COMMAND_HANDLER](#command_handler), mais mappe des commandes réfléchies à partir de la fenêtre parente.  
  
```
REFLECTED_COMMAND_HANDLER( id, code, func )
```  
  
### <a name="parameters"></a>Paramètres  
 `id`  
 [in] Identificateur de l’élément de menu, le contrôle ou l’accélérateur.  
  
 `code`  
 [in] Le code de notification.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  

##  <a name="reflected_command_id_handler"></a>REFLECTED_COMMAND_ID_HANDLER  
 Semblable à [COMMAND_ID_HANDLER](#command_id_handler), mais mappe des commandes réfléchies à partir de la fenêtre parente.  
  
```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Paramètres  
 `id`  
 [in] Identificateur de l’élément de menu, le contrôle ou l’accélérateur.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  

##  <a name="reflected_command_range_code_handler"></a>REFLECTED_COMMAND_RANGE_CODE_HANDLER  
 Semblable à [COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler), mais mappe des commandes réfléchies à partir de la fenêtre parente.  
  
```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```  
  
### <a name="parameters"></a>Paramètres  
 `idFirst`  
 [in] Marque le début d’une plage contiguë d’identificateurs de contrôle.  
  
 `idLast`  
 [in] Marque la fin d’une plage contiguë d’identificateurs de contrôle.  
  
 `code`  
 [in] Le code de notification.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  

##  <a name="reflected_command_range_handler"></a>REFLECTED_COMMAND_RANGE_HANDLER  
 Semblable à [COMMAND_RANGE_HANDLER](#command_range_handler), mais mappe des commandes réfléchies à partir de la fenêtre parente.  
  
```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Paramètres  
 `idFirst`  
 [in] Marque le début d’une plage contiguë d’identificateurs de contrôle.  
  
 `idLast`  
 [in] Marque la fin d’une plage contiguë d’identificateurs de contrôle.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  

##  <a name="reflected_notify_code_handler"></a>REFLECTED_NOTIFY_CODE_HANDLER  
 Semblable à [NOTIFY_CODE_HANDLER](#notify_code_handler), mais mappe des notifications réfléchies à partir de la fenêtre parente.  
  
```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```  
  
### <a name="parameters"></a>Paramètres  
 `cd`  
 [in] Le code de notification.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  

##  <a name="reflected_notify_handler"></a>REFLECTED_NOTIFY_HANDLER  
 Semblable à [NOTIFY_HANDLER](#notify_handler), mais mappe des notifications réfléchies à partir de la fenêtre parente.  
  
```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Paramètres  
 `id`  
 [in] Identificateur de l’élément de menu, le contrôle ou l’accélérateur.  
  
 `cd`  
 [in] Le code de notification.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  

##  <a name="reflected_notify_id_handler"></a>REFLECTED_NOTIFY_ID_HANDLER  
 Semblable à [NOTIFY_ID_HANDLER](#notify_id_handler), mais mappe des notifications réfléchies à partir de la fenêtre parente.  
  
```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Paramètres  
 `id`  
 [in] Identificateur de l’élément de menu, le contrôle ou l’accélérateur.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  

##  <a name="reflected_notify_range_code_handler"></a>REFLECTED_NOTIFY_RANGE_CODE_HANDLER  
 Semblable à [NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler), mais mappe des notifications réfléchies à partir de la fenêtre parente.  
  
```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```    
  
### <a name="parameters"></a>Paramètres  
 `idFirst`  
 [in] Marque le début d’une plage contiguë d’identificateurs de contrôle.  
  
 `idLast`  
 [in] Marque la fin d’une plage contiguë d’identificateurs de contrôle.  
  
 `cd`  
 [in] Le code de notification.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h   
  
##  <a name="reflected_notify_range_handler"></a>REFLECTED_NOTIFY_RANGE_HANDLER  
 Semblable à [NOTIFY_RANGE_HANDLER](#notify_range_handler), mais mappe des notifications réfléchies à partir de la fenêtre parente.  
  
```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Paramètres  
 `idFirst`  
 [in] Marque le début d’une plage contiguë d’identificateurs de contrôle.  
  
 `idLast`  
 [in] Marque la fin d’une plage contiguë d’identificateurs de contrôle.  
  
 `func`  
 [in] Le nom de la fonction gestionnaire de messages.  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)

