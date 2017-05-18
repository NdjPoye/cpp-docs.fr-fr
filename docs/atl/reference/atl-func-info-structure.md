---
title: Les structures _ATL_FUNC_INFO structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 7bc607931c486f3dd7a398b277048db77e9b2f62
ms.contentlocale: fr-fr
ms.lasthandoff: 03/31/2017

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
 Convention d’appel. Lors de l’utilisation de cette structure avec le [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) (classe), ce membre doit être **CC_STDCALL**. `CC_CDECL`est la seule option prise en charge dans Windows CE pour le `CALLCONV` champ le `_ATL_FUNC_INFO` structure. Toute autre valeur non pris en charge ainsi son comportement non défini.  
  
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
  
 [!code-cpp[NVC_ATL_Windowing #139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]  
  
 Vous pouvez définir un `_ATL_FUNC_INFO` structure :  
  
 [!code-cpp[NVC_ATL_Windowing #140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)   
 [IDispEventSimpleImpl (classe)](../../atl/reference/idispeventsimpleimpl-class.md)   
 [MACRO SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)






