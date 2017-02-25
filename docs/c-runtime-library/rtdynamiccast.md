---
title: "__RTDynamicCast | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__RTDynamicCast"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcrt.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__RTDynamicCast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__RTDynamicCast"
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# __RTDynamicCast
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Implémentation Runtime de l'opérateur [dynamic\_cast](../cpp/dynamic-cast-operator.md).  
  
## Syntaxe  
  
```cpp  
PVOID __RTDynamicCast (  
   PVOID inptr,   
   LONG VfDelta,  
   PVOID SrcType,  
   PVOID TargetType,   
   BOOL isReference  
   ) throw(...)  
```  
  
#### Paramètres  
 `inptr`  
 Pointeur vers un objet polymorphique.  
  
 `VfDelta`  
 Décalage du pointeur virtuel de fonction dans l'objet.  
  
 `SrcType`  
 Type statique de l'objet référencé par le paramètre `inptr`.  
  
 `TargetType`  
 Résultat attendu de conversion.  
  
 `isReference`  
 `true` si l'entrée est une référence ; `false` si l'entrée est un pointeur.  
  
## Valeur de retour  
 Pointeur vers le sous\-objet approprié, en cas de réussite ; sinon, NULL.  
  
## Exceptions  
 `bad_cast()` si l'entrée de `dynamic_cast<>` est une référence et que la conversion échoue.  
  
## Notes  
 Convertit `inptr` vers un objet de type `TargetType`.  Le type d' `inptr` doit être un pointeur si `TargetType` est un pointeur, ou une l\-value si `TargetType` est une référence.  `TargetType` doit être un pointeur ou une référence à un type de classe définie précédemment, ou un pointeur vers void.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|\_\_RTDynamicCast|rtti.h|