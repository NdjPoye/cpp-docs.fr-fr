---
title: Structure de _ATL_WIN_MODULE70 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d284f18005b470f80cc911a24ec2c813715a0ca4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
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
 Utilisé pour sérialiser l’accès au code de l’inscription de fenêtre. Utilisé en interne par ATL.  
  
 **m_pCreateWndList**  
 Permet de lier windows à leurs objets. Utilisé en interne par ATL.  
  
 **m_rgWindowClassAtoms**  
 Utilisé pour effectuer le suivi des inscriptions de classe de fenêtre afin qu’ils puissent être correctement annulées à la fin. Utilisé en interne par ATL.  
  
## <a name="remarks"></a>Notes  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) est défini comme un typedef de `_ATL_WIN_MODULE70`.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlbase.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)





