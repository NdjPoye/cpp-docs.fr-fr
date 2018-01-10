---
title: Structure de _ATL_BASE_MODULE70 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
dev_langs: C++
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a85aa23baf294f5f1f4dc2eb49c6004d7633280
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlcore.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)





