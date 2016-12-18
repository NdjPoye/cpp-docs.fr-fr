---
title: "_aligned_realloc | Microsoft Docs"
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
  - "_aligned_realloc"
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
  - "_aligned_realloc"
  - "aligned_realloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "aligned_realloc (fonction)"
  - "_aligned_realloc (fonction)"
ms.assetid: 80ce96e8-6087-416f-88aa-4dbb8cb1d218
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_realloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Modifie la taille d'un bloc de mémoire qui a été allouée avec [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) ou [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md).  
  
## Syntaxe  
  
```  
void * _aligned_realloc(  
   void *memblock,   
   size_t size,   
   size_t alignment  
);  
```  
  
#### Paramètres  
 \[in\] `memblock`  
 Le pointeur de bloc mémoire actuel.  
  
 \[in\] `size`  
 La taille de l'allocation de mémoire demandée.  
  
 \[in\] `alignment`  
 La valeur d'alignement, qui doit être une puissance entière de 2.  
  
## Valeur de retour  
 `_aligned_realloc` retourne un pointeur void sur le bloc mémoire realloué \(et éventuellement déplacé\).  La valeur de retour est `NULL` si la taille est de zéro et que l'argument de mémoire tampon n'est pas `NULL`, ou s'il n'y a pas assez de mémoire disponible pour développer le bloc jusqu'à la taille spécifiée.  Dans le premier cas, le bloc d'origine est libéré.  Dans le deuxième, le bloc d'origine reste inchangé.  Les valeur de retour pointent vers un espace de stockage, qui est garanti d'être aligné correctement pour le stockage de n'importe quel types d'objet.  Pour obtenir un pointeur sur un type autre que void, utilisez un cast de type sur la valeur de retour.  
  
 C'est une erreur de réallouer la mémoire et de modifier l'alignement d'un bloc.  
  
## Notes  
 `_aligned_realloc` est basée sur `malloc`.  Pour plus d'informations sur l'utilisation de `_aligned_offset_malloc`, consultez [](../../c-runtime-library/reference/malloc.md "malloc").  
  
 Cette fonction alloue à `errno` la valeur `ENOMEM` si l'allocation de mémoire a échoué ou si la taille demandée est supérieure à `_HEAP_MAXREQ`.  Pour plus d'informations sur `errno`, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  Aussi, `_aligned_realloc` valide ses paramètres.  Si `alignment` n'est pas une puissance de 2, cette fonction appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction renvoie `NULL` et définit `errno` avec la valeur `EINVAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_aligned_realloc`|\<malloc.h\>|  
  
## Exemple  
 Pour plus d'informations, consultez [aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md).  
  
## Voir aussi  
 [Alignement des données](../../c-runtime-library/data-alignment.md)