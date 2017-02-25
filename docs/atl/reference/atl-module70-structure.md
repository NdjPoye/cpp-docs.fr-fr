---
title: "_ATL_MODULE70 Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_MODULE70"
  - "ATL::_ATL_MODULE70"
  - "ATL._ATL_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_MODULE70 structure"
  - "ATL_MODULE70 structure"
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# _ATL_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Contient des données utilisées par chaque module ATL.  
  
## Syntaxe  
  
```  
  
      struct _ATL_MODULE70{  
   UINT cbSize;  
   LONG m_nLockCnt;  
   _ATL_TERMFUNC_ELEM* m_pTermFuncs;  
   CComCriticalSection m_csStaticDataInitAndTypeInfo;  
};  
```  
  
## Membres  
 `cbSize`  
 La taille de la structure, utilisée pour le contrôle de version.  
  
 `m_nLockCnt`  
 Nombre de références pour déterminer la durée le package doit rester actif.  
  
 **m\_pTermFuncs**  
 Fonctions de suivi qui ont été enregistrées pour être appelées lorsque ATL arrête.  
  
 **m\_csStaticDataInitAndTypeInfo**  
 Utilisé pour coordonner l'accès aux données internes dans des situations multithread.  
  
## Notes  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md) est défini comme un typedef d' `_ATL_MODULE70`.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)