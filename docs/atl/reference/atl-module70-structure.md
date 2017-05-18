---
title: Structure de _ATL_MODULE70 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
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
ms.sourcegitcommit: 4e393abb2a904a0f5e101efe3d78d0645664397b
ms.openlocfilehash: ea1d87d3d500fc08f3da16de6820ca003e899419
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="atlmodule70-structure"></a>Structure de _ATL_MODULE70
Contient les données utilisées par chaque module ATL.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct _ATL_MODULE70 {
    UINT cbSize;
    LONG m_nLockCnt;
    _ATL_TERMFUNC_ELEM* m_pTermFuncs;
    CComCriticalSection m_csStaticDataInitAndTypeInfo;
};
```  
  
## <a name="members"></a>Membres  
 `cbSize`  
 La taille de la structure utilisée pour le contrôle de version.  
  
 `m_nLockCnt`  
 Décompte de références pour déterminer la durée pendant laquelle le module doit rester actif.  
  
 **m_pTermFuncs**  
 Fonctions de pistes qui ont été inscrits pour être appelée lorsque ATL s’arrête.  
  
 **m_csStaticDataInitAndTypeInfo**  
 Utilisé pour coordonner l’accès aux données internes dans les situations multithreads.  
  
## <a name="remarks"></a>Remarques  
 [_ATL_MODULE](atl-typedefs.md#_atl_module) est défini comme un typedef de `_ATL_MODULE70`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)








