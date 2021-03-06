---
title: Structure de _ATL_BASE_MODULE70 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 484fc4a68d0421cb12e901b2d56f30e95f6cb79b
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2018
---
# <a name="atlbasemodule70-structure"></a>Structure de _ATL_BASE_MODULE70
Utilisé par aucun projet qui utilise ATL.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct _ATL_BASE_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInst;
    HINSTANCE m_hInstResource;
    bool m_bNT5orWin98;
    DWORD dwAtlBuildVer;
    GUID* pguidVer;
    CRITICAL_SECTION m_csResource;
    CSimpleArray<HINSTANCE> m_rgResourceInstance;
};
```  
  
## <a name="members"></a>Membres  
 `cbSize`  
 La taille de la structure utilisée pour le contrôle de version.  
  
 `m_hInst`  
 Le **hInstance** pour ce module (exe ou dll).  
  
 `m_hInstResource`  
 Handle de ressource d’instance par défaut.  
  
 **m_bNT5orWin98**  
 Informations de version du système d’exploitation. Utilisé en interne par ATL.  
  
 **dwAtlBuildVer**  
 Stocke la version d’ATL. Actuellement 0x0700.  
  
 **pguidVer**  
 GUID d’interne d’ATL.  
  
 **m_csResource**  
 Utilisé pour synchroniser l’accès à la **m_rgResourceInstance** tableau. Utilisé en interne par ATL.  
  
 **m_rgResourceInstance**  
 Tableau utilisé pour rechercher des ressources dans toutes les instances de ressources dont est prenant en charge ATL. Utilisé en interne par ATL.  
  
## <a name="remarks"></a>Notes  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) est défini comme un typedef de `_ATL_BASE_MODULE70`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcore.h  
  
## <a name="see-also"></a>Voir aussi  
 [Les classes et structs](../../atl/reference/atl-classes.md)





