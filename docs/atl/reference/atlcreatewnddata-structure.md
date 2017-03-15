---
title: "_AtlCreateWndData Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::_AtlCreateWndData"
  - "ATL._AtlCreateWndData"
  - "_AtlCreateWndData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_AtlCreateWndData structure"
  - "AtlCreateWndData structure"
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# _AtlCreateWndData Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette structure contient les données d'instance de classe dans le code de fenêtrage dans ATL.  
  
## Syntaxe  
  
```  
  
      struct _AtlCreateWndData{  
   void* m_pThis;  
   DWORD m_dwThreadID;  
   _AtlCreateWndData* m_pNext;  
};  
```  
  
## Membres  
 **m\_pThis**  
 Le pointeur de **this** utilisé pour accéder à l'instance de classe dans les procédures de fenêtre.  
  
 `m_dwThreadID`  
 L'ID de thread de l'instance de classe en cours.  
  
 **m\_pNext**  
 Pointeur vers l'objet d' `_AtlCreateWndData` .  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)