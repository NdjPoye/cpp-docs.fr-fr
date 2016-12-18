---
title: "_aligned_offset_malloc | Microsoft Docs"
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
  - "_aligned_offset_malloc"
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
  - "_aligned_offset_malloc"
  - "aligned_offset_malloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_aligned_offset_malloc (fonction)"
  - "aligned_offset_malloc (fonction)"
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_offset_malloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Alloue de la mémoire sur la base d'un alignement spécifié  
  
## Syntaxe  
  
```  
void * _aligned_offset_malloc(  
   size_t size,   
   size_t alignment,   
   size_t offset  
);  
```  
  
#### Paramètres  
 \[in\] `size`  
 La taille de l'allocation de mémoire demandée.  
  
 \[in\] `alignment`  
 La valeur d'alignement, qui doit être une puissance entière de 2.  
  
 \[in\] `offset`  
 L'offset dans l'allocation de mémoire pour forcer l'alignement.  
  
## Valeur de retour  
 Un pointeur vers le bloc de mémoire alloué ou `NULL` si l'opération a échoué.  
  
## Notes  
 `_aligned_offset_malloc` est utile dans les cas où il est nécessaire dans un élément imbriqué ; par exemple, si un alignement est nécessaire dans une classe imbriquée.  
  
 `_aligned_offset_malloc` est basé sur `malloc`; pour plus d'informations, consultez [malloc](../../c-runtime-library/reference/malloc.md).  
  
 `_aligned_offset_malloc` est marqué `__declspec(noalias)` et `__declspec(restrict)` ; cela signifie que la fonction ne modifiera pas de variables globales et que le pointeur retourné n'est pas sous la forme d'un alias.  Pour plus d'informations, consultez [noalias](../../cpp/noalias.md) et [restrict](../../cpp/restrict.md).  
  
 Cette fonction alloue à `errno` la valeur `ENOMEM` si l'allocation de mémoire a échoué ou si la taille demandée est supérieure à `_HEAP_MAXREQ`.  Pour plus d'informations sur `errno`, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  Aussi, `_aligned_offset_malloc` valide ses paramètres.  Si `alignment` n'est pas une puissance de 2 ou si `offset` est supérieur ou égal à `size` et une valeur différente de zéro, cette fonction appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction renvoie `NULL` et définit `errno` avec la valeur `EINVAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_aligned_offset_malloc`|\<malloc.h\>|  
  
## Exemple  
 Pour plus d'informations, consultez [aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md).  
  
## Voir aussi  
 [Alignement des données](../../c-runtime-library/data-alignment.md)