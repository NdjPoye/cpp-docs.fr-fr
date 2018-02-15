---
title: Les structures _ATL_FUNC_INFO structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
dev_langs:
- C++
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a5e184f1c78264304b8e4424ea3f9659689f333b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="atlfuncinfo-structure"></a>Les structures _ATL_FUNC_INFO structure
Contient des informations de type utilisées pour décrire une méthode ou propriété sur une dispinterface.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```  
  
## <a name="members"></a>Membres  
 **cc**  
 Convention d’appel. Lors de l’utilisation de cette structure avec le [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) (classe), ce membre doit être **CC_STDCALL**. `CC_CDECL` est la seule option prise en charge dans Windows CE pour le `CALLCONV` champ le `_ATL_FUNC_INFO` structure. Toute autre valeur non pris en charge ainsi son comportement non défini.  
  
 **vtReturn**  
 Le type variant de la fonction de valeur de retour.  
  
 **nParams**  
 Le nombre de paramètres de fonction.  
  
 **pVarTypes**  
 Tableau de types variant des paramètres de fonction.  
  
## <a name="remarks"></a>Notes  
 En interne, ATL utilise cette structure pour conserver les informations obtenues à partir d’une bibliothèque de types. Vous devrez peut-être manipuler directement de cette structure si vous fournissez des informations de type pour un gestionnaire d’événements utilisé avec le [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) classe et [macro SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) (macro).  
  
## <a name="example"></a>Exemple  
 Étant donné une méthode dispinterface définie dans un IDL :  
  
 [!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]  
  
 Vous pouvez définir un `_ATL_FUNC_INFO` structure :  
  
 [!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlcom.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)   
 [IDispEventSimpleImpl (classe)](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)





