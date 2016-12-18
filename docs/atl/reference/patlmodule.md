---
title: "_pAtlModule | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATLBASE/_pAtlModule"
  - "_pAtlModule"
  - "ATL::_pAtlModule"
  - "ATL._pAtlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_pAtlModule variable"
  - "pAtlModule variable"
ms.assetid: 0ecde3a9-3f4d-4c7b-bb54-713ce05c4777
caps.latest.revision: 13
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _pAtlModule
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une variable globale stockant un pointeur vers le module actuel.  
  
## Syntaxe  
  
```  
__declspec(selectany) CAtlModule * _pAtlModule  
```  
  
## Notes  
 Les méthodes sur cette variable globale peuvent être utilisées pour fournir des fonctionnalités que la classe \( maintenant obsolète\) [CComModule](../../atl/reference/ccommodule-class.md) est fournie dans Visual C\+\+ 6,0.  
  
## Exemple  
 [!code-cpp[NVC_ATL_Windowing#97](../../atl/codesnippet/CPP/patlmodule_1.cpp)]  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Global Variables](../../atl/reference/atl-global-variables.md)