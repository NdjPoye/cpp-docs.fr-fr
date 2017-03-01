---
title: Macros de mappage COM | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 79658b6ac22719af7172c9d2848675faf2a23a0c
ms.lasthandoff: 02/24/2017

---
# <a name="com-map-macros"></a>Macros de mappage COM
Ces macros définissent des mappages d’interfaces COM.  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|Marque le début des entrées de mappage d’interface COM.|  
|[COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)|Entre les interfaces dans le mappage d’interface COM.|  
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|Utiliser cette macro pour distinguer les deux branches de l’héritage.|  
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|Utilisez la macro pour entrer dans l’interface de la carte de COM et spécifier son IID.|  
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|Identique à [COM_INTERFACE_ENTRY2](#com_interface_entry2), mais vous pouvez spécifier un IID différents.|  
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|Lorsque l’interface est identifié par `iid` est interrogée, `COM_INTERFACE_ENTRY_AGGREGATE` transfère à `punk`.|  
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|Identique à [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), sauf que l’interrogation pour les IID entraîne transmettant à `punk`.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|Identique à [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), sauf si `punk` est **NULL**, il crée automatiquement l’agrégat décrite par le `clsid`.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|Identique à [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), sauf que l’interrogation pour les IID entraîne la requête de transfert `punk`et si `punk` est **NULL**, sont automatiquement la création de l’agrégat décrite par le `clsid`.|  
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Entraîne l’appel de votre programme [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) lorsque l’interface spécifiée est demandé.|  
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Enregistre les données spécifiques à l’interface pour chaque instance.|  
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Expose des interfaces détachables.|  
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|Traite le mappage COM de la classe de base lorsque le traitement atteint cette entrée dans le mappage COM.|  
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|Un mécanisme général pour se connecter à ATL `QueryInterface` logique.|  
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|Identique à [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), sauf que l’interrogation pour les IID entraîne un appel à `func`.|  
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|Retourne **E_NOINTERFACE** et s’arrête COM carte traitement lorsque l’interface spécifiée est recherché.|  
|[END_COM_MAP](#end_com_map)|Marque la fin des entrées de mappage d’interface COM.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
   
##  <a name="a-namebegincommapa--begincommap"></a><a name="begin_com_map"></a>BEGIN_COM_MAP  
 Le mappage COM est un mécanisme qui expose des interfaces sur un objet à un client via `QueryInterface`.  
  
```
BEGIN_COM_MAP(x)
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Le nom de l’objet de classe que vous exposez des interfaces sur.  
  
### <a name="remarks"></a>Remarques  
 [CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) renvoie uniquement les pointeurs des interfaces dans la table COM. Démarrer votre carte d’interface avec le `BEGIN_COM_MAP` macro, ajoutez des entrées pour chacun de vos interfaces avec la [COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/c5363b8b-a1a2-471e-ad3a-d472f6c356c5) macro ou une de ses variantes et effectuer un mappage avec le [END_COM_MAP](#end_com_map) (macro).  

  
### <a name="example"></a>Exemple  
 À partir de la bibliothèque ATL [BEEPER](../../visual-cpp-samples.md) exemple :  
  
 [!code-cpp[NVC_ATL_COM N °&1;](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="a-namecominterfaceentrymacrosa--cominterfaceentry-macros"></a><a name="com_interface_entry_macros"></a>Macros COM_INTERFACE_ENTRY  
 Ces macros entrer des interfaces d’un objet dans son mappage COM afin qu’ils sont accessibles par `QueryInterface`. L’ordre des entrées dans la table COM est que les interfaces de commande ne fonctionnera pas une correspondance **IID** pendant `QueryInterface`.  
  
##  <a name="a-namecominterfaceentry2x2a--cominterfaceentry2"></a><a name="com_interface_entry2_x2"></a>COM_INTERFACE_ENTRY2  
 Utiliser cette macro pour distinguer les deux branches de l’héritage.  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Le nom d’une interface que vous souhaitez exposer à partir de votre objet.  
  
 `x2`  
 [in] Le nom de la branche de l’héritage à partir de laquelle *x* est exposé.  
  
### <a name="remarks"></a>Remarques  
 Par exemple, si vous dérivez votre objet de classe à partir de deux interfaces doubles, vous exposez `IDispatch` à l’aide de `COM_INTERFACE_ENTRY2` depuis `IDispatch` peut être obtenu à partir de l’une des interfaces.  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#118;](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="a-namecominterfaceentryiida--cominterfaceentryiid"></a><a name="com_interface_entry_iid"></a>COM_INTERFACE_ENTRY_IID  
 Utilisez la macro pour entrer dans l’interface de la carte de COM et spécifier son IID.  
  
```
COM_INTERFACE_ENTRY_IID(iid, x)
```  
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Le GUID de l’interface exposée.  
  
 *x*  
 [in] Le nom de la classe dont vtable sera exposée en tant que l’interface identifié par `iid`.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#117;](../../atl/codesnippet/cpp/com-map-macros_3.h)]  
  
##  <a name="a-namecominterfaceentry2iida--cominterfaceentry2iid"></a><a name="com_interface_entry2_iid"></a>COM_INTERFACE_ENTRY2_IID  
 Identique à [COM_INTERFACE_ENTRY2](#com_interface_entry2), mais vous pouvez spécifier un IID différents.  
  
```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```   
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Le GUID que vous spécifiez pour l’interface.  
  
 *x*  
 [in] Le nom d’une interface qui dérive directement de votre objet de classe.  
  
 `x2`  
 [in] Le nom d’une deuxième interface qui dérive directement de votre objet de classe.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
##  <a name="a-namecominterfaceentry2a--cominterfaceentry2"></a><a name="com_interface_entry2"></a>COM_INTERFACE_ENTRY2  
 Utiliser cette macro pour distinguer les deux branches de l’héritage.  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Le nom d’une interface que vous souhaitez exposer à partir de votre objet.  
  
 `x2`  
 [in] Le nom de la branche de l’héritage à partir de laquelle *x* est exposé.  
  
### <a name="remarks"></a>Remarques  
 Par exemple, si vous dérivez votre objet de classe à partir de deux interfaces doubles, vous exposez `IDispatch` à l’aide de `COM_INTERFACE_ENTRY2` depuis `IDispatch` peut être obtenu à partir de l’une des interfaces.  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#118;](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="a-namecominterfaceentryaggregate2a--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate2"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 Lorsque l’interface est identifié par `iid` est interrogée, `COM_INTERFACE_ENTRY_AGGREGATE` transfère à `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Le GUID de l’interface demandé.  
  
 `punk`  
 [in] Le nom d’un **IUnknown** pointeur.  
  
### <a name="remarks"></a>Notes  
 Le `punk` paramètre est censé pour pointer vers l’inconnu intérieur d’un agrégat ou à **NULL**, auquel cas l’entrée est ignorée. En règle générale, vous devez **CoCreate** l’agrégat dans `FinalConstruct`.  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryaggregateblinda--cominterfaceentryaggregateblind"></a><a name="com_interface_entry_aggregate_blind"></a>COM_INTERFACE_ENTRY_AGGREGATE_BLIND  
 Identique à [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), sauf que l’interrogation pour les IID entraîne transmettant à `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```  
  
### <a name="parameters"></a>Paramètres  
 `punk`  
 [in] Le nom d’un **IUnknown** pointeur.  
  
### <a name="remarks"></a>Remarques  
 Si l’interface de requête échoue, le traitement du mappage COM se poursuit.  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#113;](../../atl/codesnippet/cpp/com-map-macros_5.h)]  
  
##  <a name="a-namecominterfaceentryaggregate3a--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate3"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 Lorsque l’interface est identifié par `iid` est interrogée, `COM_INTERFACE_ENTRY_AGGREGATE` transfère à `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Le GUID de l’interface demandé.  
  
 `punk`  
 [in] Le nom d’un **IUnknown** pointeur.  
  
### <a name="remarks"></a>Remarques  
 Le `punk` paramètre est censé pour pointer vers l’inconnu intérieur d’un agrégat ou à **NULL**, auquel cas l’entrée est ignorée. En règle générale, vous devez **CoCreate** l’agrégat dans `FinalConstruct`.  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregatea--cominterfaceentryautoaggregate"></a><a name="com_interface_entry_autoaggregate"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 Identique à [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), sauf si `punk` est **NULL**, il crée automatiquement l’agrégat décrite par le `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Le GUID de l’interface demandé.  
  
 `punk`  
 [in] Le nom d’un **IUnknown** pointeur. Doit être un membre de la classe contenant le mappage COM.  
  
 `clsid`  
 [in] L’identificateur de l’agrégat qui sera créé si `punk` est **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#114;](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="a-namecominterfaceentryaggregatea--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 Lorsque l’interface est identifié par `iid` est interrogée, `COM_INTERFACE_ENTRY_AGGREGATE` transfère à `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Le GUID de l’interface demandé.  
  
 `punk`  
 [in] Le nom d’un **IUnknown** pointeur.  
  
### <a name="remarks"></a>Remarques  
 Le `punk` paramètre est censé pour pointer vers l’inconnu intérieur d’un agrégat ou à **NULL**, auquel cas l’entrée est ignorée. En règle générale, vous devez **CoCreate** l’agrégat dans `FinalConstruct`.  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregateblinda--cominterfaceentryautoaggregateblind"></a><a name="com_interface_entry_autoaggregate_blind"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND  
 Identique à [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), sauf que l’interrogation pour les IID entraîne la requête de transfert `punk`et si `punk` est **NULL**, sont automatiquement la création de l’agrégat décrite par le `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```  
  
### <a name="parameters"></a>Paramètres  
 `punk`  
 [in] Le nom d’un **IUnknown** pointeur. Doit être un membre de la classe contenant le mappage COM.  
  
 `clsid`  
 [in] L’identificateur de l’agrégat qui sera créé si `punk` est **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Si l’interface de requête échoue, le traitement du mappage COM se poursuit.  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#115;](../../atl/codesnippet/cpp/com-map-macros_7.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregate2a--cominterfaceentryautoaggregate"></a><a name="com_interface_entry_autoaggregate2"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 Identique à [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), sauf si `punk` est **NULL**, il crée automatiquement l’agrégat décrite par le `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Le GUID de l’interface demandé.  
  
 `punk`  
 [in] Le nom d’un **IUnknown** pointeur. Doit être un membre de la classe contenant le mappage COM.  
  
 `clsid`  
 [in] L’identificateur de l’agrégat qui sera créé si `punk` est **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#114;](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="a-namecominterfaceentrybreaka--cominterfaceentrybreak"></a><a name="com_interface_entry_break"></a>COM_INTERFACE_ENTRY_BREAK  
 Entraîne l’appel de votre programme [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) lorsque l’interface spécifiée est demandé.  
  
```
COM_INTERFACE_ENTRY_BREAK(x)
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Texte utilisé pour construire l’identificateur d’interface.  
  
### <a name="remarks"></a>Remarques  
 L’interface IID est construit en ajoutant *x* à `IID_`. Par exemple, si *x* est `IPersistStorage`, l’IID sera `IID_IPersistStorage`.  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
##  <a name="a-namecominterfaceentrycachedtearoffa--cominterfaceentrycachedtearoff"></a><a name="com_interface_entry_cached_tear_off"></a>COM_INTERFACE_ENTRY_CACHED_TEAR_OFF  
 Enregistre les données spécifiques à l’interface pour chaque instance.  
  
```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```   
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Le GUID de l’interface détachables.  
  
 *x*  
 [in] Le nom de la classe qui implémente l’interface.  
  
 `punk`  
 [in] Le nom d’un **IUnknown** pointeur. Doit être un membre de la classe contenant le mappage COM. Doit être initialisé pour **NULL** dans le constructeur de l’objet de classe.  
  
### <a name="remarks"></a>Notes  
 Si l’interface n’est pas utilisée, cela réduit la taille d’instance globale de votre objet.  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_COM&#54;](../../atl/codesnippet/cpp/com-map-macros_8.h)]  
  
##  <a name="a-namecominterfaceentrytearoffa--cominterfaceentrytearoff"></a><a name="com_interface_entry_tear_off"></a>COM_INTERFACE_ENTRY_TEAR_OFF  
 Expose des interfaces détachables.  
  
```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```  
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Le GUID de l’interface détachables.  
  
 *x*  
 [in] Le nom de la classe qui implémente l’interface.  
  
### <a name="remarks"></a>Remarques  
 Une interface détachable est implémentée comme un objet distinct est instancié chaque fois que l’interface qu’il représente est interrogé pour. En général, vous générez votre interface comme une détachables si l’interface est rarement utilisée, étant donné que cette action enregistre un pointeur vtable dans chaque instance de votre objet principal. Le volant est supprimé lorsque son décompte de références est égal à zéro. La classe qui implémente le détachables doit être dérivée de `CComTearOffObjectBase` et avoir sa propre table COM.  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_COM N °&1;](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="a-namecominterfaceentrychaina--cominterfaceentrychain"></a><a name="com_interface_entry_chain"></a>COM_INTERFACE_ENTRY_CHAIN  
 Traite le mappage COM de la classe de base lorsque le traitement atteint cette entrée dans le mappage COM.  
  
```
COM_INTERFACE_ENTRY_CHAIN(classname)
```  
  
### <a name="parameters"></a>Paramètres  
 *nom de classe*  
 [in] Une classe de base de l’objet actuel.  
  
### <a name="remarks"></a>Remarques  
 Par exemple, dans le code suivant :  
  
 [!code-cpp[NVC_ATL_Windowing&#116;](../../atl/codesnippet/cpp/com-map-macros_9.h)]  
  
 Notez que la première entrée dans la table COM doit être une interface sur l’objet qui contient le mappage COM. Par conséquent, vous ne pouvez démarrer vos entrées de mappage COM avec `COM_INTERFACE_ENTRY_CHAIN`, ce qui provoque le mappage COM d’un autre objet à rechercher au point où **COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)** apparaît dans la table de l’objet COM. Si vous souhaitez rechercher le mappage d’un autre objet COM tout d’abord, ajoutez une entrée de l’interface pour **IUnknown** à votre mappage COM, puis chaîne mappage COM de l’autre objet. Exemple :  
  
 [!code-cpp[NVC_ATL_Windowing&#111;](../../atl/codesnippet/cpp/com-map-macros_10.h)]  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
##  <a name="a-namecominterfaceentryfunc2a--cominterfaceentryfunc"></a><a name="com_interface_entry_func2"></a>COM_INTERFACE_ENTRY_FUNC  
 Un mécanisme général pour se connecter à ATL `QueryInterface` logique.  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Le GUID de l’interface exposée.  
  
 `dw`  
 [in] Un paramètre passé à la `func`.  
  
 `func`  
 [in] Le pointeur de fonction qui renvoie `iid`.  
  
### <a name="remarks"></a>Remarques  
 Si *iid* correspond à l’IID de l’interface demandé, puis la fonction spécifiée par `func` est appelée. La déclaration de la fonction doit être :  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 Lorsque votre fonction est appelée, `pv` pointe vers l’objet de classe. Le `riid` paramètre fait référence à l’interface demandée, `ppv` est le pointeur vers l’emplacement dans lequel la fonction doit stocker le pointeur vers l’interface, et `dw` est le paramètre que vous avez spécifié dans l’entrée. La fonction doit définir \* `ppv` à **NULL** et retourner **E_NOINTERFACE** ou **S_FALSE** si elle choisit de ne pas renvoyer une interface. Avec **E_NOINTERFACE**, traitement de mappage COM se termine. Avec **S_FALSE**, traitement de mappage COM se poursuit, même si aucun pointeur d’interface a été retourné. Si la fonction retourne un pointeur d’interface, elle doit retourner `S_OK`.  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
##  <a name="a-namecominterfaceentryfuncblinda--cominterfaceentryfuncblind"></a><a name="com_interface_entry_func_blind"></a>COM_INTERFACE_ENTRY_FUNC_BLIND  
 Identique à [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), sauf que l’interrogation pour les IID entraîne un appel à `func`.  
  
```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```  
  
### <a name="parameters"></a>Paramètres  
 `dw`  
 [in] Un paramètre passé à la `func`.  
  
 `func`  
 [in] La fonction qui est appelée lors du traitement de cette entrée dans le mappage COM.  
  
### <a name="remarks"></a>Remarques  
 Tout échec entraîne le traitement de continuer sur la carte COM. Si la fonction retourne un pointeur d’interface, elle doit retourner `S_OK`.  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
##  <a name="a-namecominterfaceentryfunca--cominterfaceentryfunc"></a><a name="com_interface_entry_func"></a>COM_INTERFACE_ENTRY_FUNC  
 Un mécanisme général pour se connecter à ATL `QueryInterface` logique.  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Le GUID de l’interface exposée.  
  
 `dw`  
 [in] Un paramètre passé à la `func`.  
  
 `func`  
 [in] Le pointeur de fonction qui renvoie `iid`.  
  
### <a name="remarks"></a>Remarques  
 Si *iid* correspond à l’IID de l’interface demandé, puis la fonction spécifiée par `func` est appelée. La déclaration de la fonction doit être :  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 Lorsque votre fonction est appelée, `pv` pointe vers l’objet de classe. Le `riid` paramètre fait référence à l’interface demandée, `ppv` est le pointeur vers l’emplacement dans lequel la fonction doit stocker le pointeur vers l’interface, et `dw` est le paramètre que vous avez spécifié dans l’entrée. La fonction doit définir \* `ppv` à **NULL** et retourner **E_NOINTERFACE** ou **S_FALSE** si elle choisit de ne pas renvoyer une interface. Avec **E_NOINTERFACE**, traitement de mappage COM se termine. Avec **S_FALSE**, traitement de mappage COM se poursuit, même si aucun pointeur d’interface a été retourné. Si la fonction retourne un pointeur d’interface, elle doit retourner `S_OK`.  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
##  <a name="a-namecominterfaceentrynointerfacea--cominterfaceentrynointerface"></a><a name="com_interface_entry_nointerface"></a>COM_INTERFACE_ENTRY_NOINTERFACE  
 Retourne **E_NOINTERFACE** et s’arrête COM carte traitement lorsque l’interface spécifiée est recherché.  
  
```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Texte utilisé pour construire l’identificateur d’interface.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez utiliser cette macro pour empêcher une interface d’être utilisés dans un cas particulier. Par exemple, vous pouvez insérer la macro dans votre COM juste avant de mapper `COM_INTERFACE_ENTRY_AGGREGATE_BLIND` à une requête pour l’interface empêcher le transfert Unknown interne de l’agrégat.  
  
 L’interface IID est construit en ajoutant *x* à `IID_`. Par exemple, si *x* est `IPersistStorage`, l’IID sera `IID_IPersistStorage`.  
  
 Consultez la page [Macros COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) des remarques sur COM entrées de la table.  
  
##  <a name="a-nameendcommapa--endcommap"></a><a name="end_com_map"></a>END_COM_MAP  
 Met fin à la définition de votre mappage d’interface COM.  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)   
 [Fonctions globales de mappage COM](../../atl/reference/com-map-global-functions.md)

