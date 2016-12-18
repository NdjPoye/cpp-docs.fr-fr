---
title: "_callnewh | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_callnewh"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_callnewh"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_callnewh"
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _callnewh
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelle *le gestionnaire*actuellement installé.  
  
## Syntaxe  
  
```cpp  
int _callnewh(  
   size_t size  
   )  
  
```  
  
#### Paramètres  
 `size`  
 La quantité de mémoire que le [nouvel opérateur](../../cpp/new-operator-cpp.md) a essayé d'allouer.  
  
## Valeur de retour  
  
|Valeur|Description|  
|------------|-----------------|  
|0|Échec : Les deux ou aucun nouveau gestionnaire n'est installé ou aucun nouveau gestionnaire n'est actif.|  
|1|Succès : Le gestionnaire est installé et actif.  L'allocation de mémoire peut être réessayée.|  
  
## Exceptions  
 Cette fonction lève [bad\_alloc](../../standard-library/bad-alloc-class.md) si *le gestionnaire* ne peut pas être localisé.  
  
## Notes  
 Le *nouveau gestionnaire* est appelé si cas de échec de [nouvel opérateur](../../cpp/new-operator-cpp.md) pour allouer correctement la mémoire.  Le nouveau gestionnaire peut ensuite initialiser une action appropriée, telle que la libération de mémoire pour que les allocations suivantes réussissent.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|\_callnewh|internal.h|  
  
## Voir aussi  
 [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md)   
 [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md)