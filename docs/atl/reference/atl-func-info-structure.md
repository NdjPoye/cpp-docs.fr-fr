---
title: Les structures _ATL_FUNC_INFO structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: c18e1c5a41ef910cfe327fdbdd8d8885ef30a092
ms.lasthandoff: 02/24/2017

---
# <a name="atlfuncinfo-structure"></a>Les structures _ATL_FUNC_INFO structure
Contient des informations de type permet de décrire une méthode ou propriété sur une dispinterface.  
  
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
 Convention d’appel. Lors de l’utilisation de cette structure avec la [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) (classe), ce membre doit être **CC_STDCALL**. `CC_CDECL`est la seule option prise en charge par Windows CE pour la `CALLCONV` champ le `_ATL_FUNC_INFO` structure. Toute autre valeur non pris en charge ainsi son comportement non défini.  
  
 **vtReturn**  
 Le type variant de la fonction de valeur de retour.  
  
 **nParams**  
 Le nombre de paramètres de fonction.  
  
 **pVarTypes**  
 Un tableau de types variants des paramètres de fonction.  
  
## <a name="remarks"></a>Remarques  
 ATL utilise en interne, cette structure pour conserver les informations obtenues à partir d’une bibliothèque de types. Vous devrez peut-être manipuler cette structure directement si vous fournissez des informations de type pour un gestionnaire d’événements utilisé avec le [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) classe et [macro SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7) (macro).  
  
## <a name="example"></a>Exemple  
 Selon une méthode dispinterface définie dans le fichier IDL :  
  
 [!code-cpp[NVC_ATL_Windowing&#139;](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]  
  
 Vous devez définir un `_ATL_FUNC_INFO` structure :  
  
 [!code-cpp[NVC_ATL_Windowing&#140;](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)   
 [IDispEventSimpleImpl (classe)](../../atl/reference/idispeventsimpleimpl-class.md)   
 [MACRO SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7)






