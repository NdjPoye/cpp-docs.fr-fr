---
title: Structure de _ATL_WIN_MODULE70 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
caps.latest.revision: 15
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
ms.sourcegitcommit: 4e393abb2a904a0f5e101efe3d78d0645664397b
ms.openlocfilehash: 383384c8f08b98592f92b5d38850137c1c0c6d54
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="atlwinmodule70-structure"></a>Structure de _ATL_WIN_MODULE70
Utilisé par le code de fenêtrage dans ATL.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct _ATL_WIN_MODULE70 {
    UNIT cbSize; 
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```  
  
## <a name="members"></a>Membres  
 `cbSize`  
 La taille de la structure utilisée pour le contrôle de version.  
  
 `m_csWindowCreate`  
 Utilisé pour sérialiser l’accès au code d’inscription de fenêtre. Utilisé en interne par ATL.  
  
 **m_pCreateWndList**  
 Permet de lier windows à leurs objets. Utilisé en interne par ATL.  
  
 **m_rgWindowClassAtoms**  
 Permet de suivre les enregistrements de classe de fenêtre afin qu’ils puissent être correctement annulées à la fin. Utilisé en interne par ATL.  
  
## <a name="remarks"></a>Remarques  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) est défini comme un typedef de `_ATL_WIN_MODULE70`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)






