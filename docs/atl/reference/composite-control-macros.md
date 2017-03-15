---
title: "Macros de contrôle composite | Documents Microsoft"
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
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
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
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: 9fb8a907c8052c9816d6b87247e903a63f34a5be
ms.lasthandoff: 02/24/2017

---
# <a name="composite-control-macros"></a>Macros de contrôle composite
Ces macros définissent des tables de récepteurs d’événements et des entrées.  
  
|||  
|-|-|  
|[BEGIN_SINK_MAP](#begin_sink_map)|Marque le début de la table de récepteur d’événements pour le contrôle composite.|  
|[END_SINK_MAP](#end_sink_map)|Marque la fin de la table de récepteur d’événements pour le contrôle composite.|  
|[AIDE DE SINK_ENTRY](#sink_entry)|Entrée à la table de récepteur d’événements.|  
|[SINK_ENTRY_EX](#sink_entry_ex)|Entrée de la table de récepteur d’événement avec un paramètre supplémentaire.| 
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017) Semblable à SINK_ENTRY_EX sauf qu’elle prend un pointeur vers l’iid.|  
|[MACRO SINK_ENTRY_INFO](#sink_entry_info)|Entrée à la table de récepteur d’événements avec les informations de type fourni manuellement pour une utilisation avec [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md).|  
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017) Similaire à la macro SINK_ENTRY_INFO sauf qu’elle prend un pointeur vers l’iid.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  

##  <a name="a-namebeginsinkmapa--beginsinkmap"></a><a name="begin_sink_map"></a>BEGIN_SINK_MAP  
 Déclare le début de la table de récepteur d’événements pour le contrôle composite.  
  
```
BEGIN_SINK_MAP(_class)
```  
  
### <a name="parameters"></a>Paramètres  
 `_class`  
 [in] Spécifie le contrôle.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#104;](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Remarques  
 Implémentation de CE ATL de ActiveX événement récepteurs uniquement prend en charge valeurs de retour de type HRESULT ou void à partir de vos méthodes de gestionnaire d’événements ; toute autre valeur de retour non pris en charge et son comportement est indéfini.  
  
##  <a name="a-nameendsinkmapa--endsinkmap"></a><a name="end_sink_map"></a>END_SINK_MAP  
 Déclare la fin de la table de récepteur d’événements pour le contrôle composite.  
  
```
END_SINK_MAP()
```  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#104;](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Remarques  
 Implémentation de CE ATL de ActiveX événement récepteurs uniquement prend en charge valeurs de retour de type HRESULT ou void à partir de vos méthodes de gestionnaire d’événements ; toute autre valeur de retour non pris en charge et son comportement est indéfini.  
  
##  <a name="a-namesinkentrya--sinkentry"></a><a name="sink_entry"></a>AIDE DE SINK_ENTRY  
 Déclare la fonction de gestionnaire ( `fn`) pour l’événement spécifié ( `dispid`), du contrôle identifié par `id`.  
  
```
SINK_ENTRY( id, dispid, fn )
```  
  
### <a name="parameters"></a>Paramètres  
 `id`  
 [in] Identifie le contrôle.  
  
 `dispid`  
 [in] Identifie l’événement spécifié.  
  
 `fn`  
 [in] Nom de la fonction de gestionnaire d’événements. Cette fonction doit utiliser le **_stdcall** convention d’appel et avoir la signature de type dispinterface approprié.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#104;](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Notes  
 Implémentation de CE ATL de ActiveX événement récepteurs uniquement prend en charge valeurs de retour de type HRESULT ou void à partir de vos méthodes de gestionnaire d’événements ; toute autre valeur de retour non pris en charge et son comportement est indéfini.  
  
##  <a name="a-namesinkentryexa--sinkentryex-and-sinkentryexp"></a><a name="sink_entry_ex"></a>SINK_ENTRY_EX et SINK_ENTRY_EX_P
 Déclare la fonction de gestionnaire ( `fn`) pour l’événement spécifié ( `dispid`), de l’interface de dispatch ( *iid)*, pour le contrôle identifié par `id`.  
  
```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Paramètres  
 `id`  
 [in] Identifie le contrôle.  
  
 `iid`  
 [in] Identifie l’interface de dispatch.  

 `piid`  
 [in] Pointeur vers l’interface de dispatch.  
  
 `dispid`  
 [in] Identifie l’événement spécifié.  
  
 `fn`  
 [in] Nom de la fonction de gestionnaire d’événements. Cette fonction doit utiliser le **_stdcall** convention d’appel et avoir la signature de type dispinterface approprié.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#136;](../../atl/codesnippet/cpp/composite-control-macros_2.h)]  
  
### <a name="remarks"></a>Remarques  
 Implémentation de CE ATL de ActiveX événement récepteurs uniquement prend en charge valeurs de retour de type HRESULT ou void à partir de vos méthodes de gestionnaire d’événements ; toute autre valeur de retour non pris en charge et son comportement est indéfini.  
  
##  <a name="a-namesinkentryinfoa--sinkentryinfo-and-sinkentryinfop"></a><a name="sink_entry_info"></a>Macro SINK_ENTRY_INFO et SINK_ENTRY_INFO_P  
 Utilisez le `SINK_ENTRY_INFO` macro au sein d’une table de récepteur d’événements pour fournir les informations requises par [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) pour acheminer les événements vers la fonction gestionnaire approprié.  
  
```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Paramètres  
 `id`  
 [in] Entier non signé identifier la source d’événements. Cette valeur doit correspondre à la `nID` utilisé dans le paramètre du modèle [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) classe de base.  
  
 `iid`  
 [in] IID qui identifie l’interface de dispatch.  

 `piid`  
 [in] Pointeur vers l’IID qui identifie l’interface de dispatch.
  
 `dispid`  
 [in] DISPID identifiant l’événement spécifié.  
  
 `fn`  
 [in] Nom de la fonction de gestionnaire d’événements. Cette fonction doit utiliser le **_stdcall** convention d’appel et avoir la signature de type dispinterface approprié.  
  
 `info`  
 [in] Tapez les informations de la fonction de gestionnaire d’événements. Ces informations de type sont fournies sous la forme d’un pointeur vers un `_ATL_FUNC_INFO` structure. `CC_CDECL`est la seule option prise en charge par Windows CE pour la `CALLCONV` champ le `_ATL_FUNC_INFO` structure. Toute autre valeur non pris en charge ainsi son comportement non défini.  
  
### <a name="remarks"></a>Notes  
 Les paramètres de quatre premiers macro sont les mêmes que ceux de la [SINK_ENTRY_EX](#sink_entry_ex) (macro). Le paramètre final fournit des informations de type pour l’événement. Implémentation de CE ATL de ActiveX événement récepteurs uniquement prend en charge valeurs de retour de type HRESULT ou void à partir de vos méthodes de gestionnaire d’événements ; toute autre valeur de retour non pris en charge et son comportement est indéfini.  
  

## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)   
 [Fonctions globales de contrôle composite](../../atl/reference/composite-control-global-functions.md)

