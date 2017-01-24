---
title: "_ATL_WIN_MODULE70 Structure | Microsoft Docs"
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
  - "_ATL_WIN_MODULE70"
  - "ATL::_ATL_WIN_MODULE70"
  - "ATL._ATL_WIN_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_WIN_MODULE70 structure"
  - "ATL_WIN_MODULE70 structure"
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
caps.latest.revision: 15
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _ATL_WIN_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé par le code de fenêtrage dans ATL.  
  
## Syntaxe  
  
```  
  
      struct _ATL_WIN_MODULE70{  
   UNIT cbSize;  
   CRITICAL_SECTION m_csWindowCreate;  
   _AtlCreateWndData* m_pCreateWndList;  
   CSimpleArray<ATOM> m_rgWindowClassAtoms;  
};  
```  
  
## Membres  
 `cbSize`  
 La taille de la structure, utilisée pour le contrôle de version.  
  
 `m_csWindowCreate`  
 Utilisé pour sérialiser l'accès au code d'alignement de la fenêtre.  Utilisé en interne par ATL.  
  
 **m\_pCreateWndList**  
 Utilisé pour lier des fenêtres à leurs objets.  Utilisé en interne par ATL.  
  
 **m\_rgWindowClassAtoms**  
 Utilisé pour suivre les inscriptions de classe de fenêtre afin qu'ils puissent être correctement annulés un enregistrement à l'arrêt.  Utilisé en interne par ATL.  
  
## Notes  
 [\_ATL\_WIN\_MODULE](../Topic/_ATL_WIN_MODULE.md) est défini comme un typedef d' `_ATL_WIN_MODULE70`.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)