---
title: Fonctions globales de mappage COM | Documents Microsoft
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
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
caps.latest.revision: 19
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: d6f23de1a5fd13d61d376acded35f9217d0a898d
ms.lasthandoff: 03/31/2017

---
# <a name="com-map-global-functions"></a>Fonctions globales de mappage COM
Ces fonctions fournissent la prise en charge pour le mappage COM **IUnknown** implémentations.  
  
|||  
|-|-|  
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|Délègue à la **IUnknown** d’un objet brutes et non agrégée.|  
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Génère un code efficace pour comparer des interfaces à **IUnknown**.|  

  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  

##  <a name="atlinternalqueryinterface"></a>AtlInternalQueryInterface  
 Récupère un pointeur vers l'interface demandée.  
  
```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `pThis`  
 [in] Un pointeur vers l’objet qui contient le mappage COM des interfaces exposées à `QueryInterface`.  
  
 `pEntries`  
 [in] Un tableau de **_ATL_INTMAP_ENTRY** structures qui accèdent à un mappage des interfaces disponibles.  
  
 `iid`  
 [in] Le GUID de l’interface demandée.  
  
 `ppvObject`  
 [out] Un pointeur vers le pointeur d’interface spécifié dans `iid`, ou **NULL** si l’interface est introuvable.  
  
### <a name="return-value"></a>Valeur de retour  
 Une des valeurs HRESULT standards.  
  
### <a name="remarks"></a>Remarques  
 `AtlInternalQueryInterface` gère seulement des interfaces dans le tableau de mappage COM. Si votre objet est agrégée, `AtlInternalQueryInterface` ne délègue pas à inconnu externe. Vous pouvez entrer des interfaces dans la table de mappage COM avec la macro [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) ou une de ses variantes.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing #94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]  
  
##  <a name="inlineisequaliunknown"></a>InlineIsEqualIUnknown  
 Appelez cette fonction, dans le cas particulier du test de **IUnknown**.  
  
```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```  
  
### <a name="parameters"></a>Paramètres  
 *rguid1*  
 [in] Le GUID à comparer à **IID_IUnknown**.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)   
 [Macros de mappage COM](../../atl/reference/com-map-macros.md)

