---
title: "_ATL_BASE_MODULE70 Structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::_ATL_BASE_MODULE70"
  - "ATL._ATL_BASE_MODULE70"
  - "_ATL_BASE_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_BASE_MODULE70 structure"
  - "ATL_BASE_MODULE70 structure"
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
caps.latest.revision: 15
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _ATL_BASE_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé par un projet qui utilise ATL.  
  
## Syntaxe  
  
```  
  
      struct _ATL_BASE_MODULE70{  
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
  
## Membres  
 `cbSize`  
 La taille de la structure, utilisée pour le contrôle de version.  
  
 `m_hInst`  
 **hInstance** pour ce module \(exe ou DLL\).  
  
 `m_hInstResource`  
 Handle de la ressource d'instance par défaut.  
  
 **m\_bNT5orWin98**  
 Informations relatives à la version du système d'exploitation.  Utilisé en interne par ATL.  
  
 **dwAtlBuildVer**  
 Stocke la version ATL.  Actuellement 0x0700.  
  
 **pguidVer**  
 GUID interne ATL.  
  
 **m\_csResource**  
 Utilisé pour synchroniser l'accès au tableau de **m\_rgResourceInstance** .  Utilisé en interne par ATL.  
  
 **m\_rgResourceInstance**  
 Rangez utilisé pour rechercher les ressources dans toutes les instances de ressource dont ATL s'aperçoit.  Utilisé en interne par ATL.  
  
## Notes  
 [\_ATL\_BASE\_MODULE](../Topic/_ATL_BASE_MODULE.md) est défini comme un typedef d' `_ATL_BASE_MODULE70`.  
  
## Configuration requise  
 **Header:** atlcore.h  
  
## Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)