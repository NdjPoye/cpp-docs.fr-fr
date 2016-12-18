---
title: "_aligned_offset_realloc | Microsoft Docs"
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
  - "_aligned_offset_realloc"
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
  - "aligned_offset_realloc"
  - "_aligned_offset_realloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "aligned_offset_realloc (fonction)"
  - "_aligned_offset_realloc (fonction)"
ms.assetid: e0263533-991e-41b0-acc9-1b8a51ab9ecd
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_offset_realloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Modifie la taille d'un bloc de mémoire qui a été allouée avec [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) ou [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md).  
  
## Syntaxe  
  
```  
void * _aligned_offset_realloc(  
   void *memblock,   
   size_t size,   
   size_t alignment,  
   size_t offset  
);  
```  
  
#### Paramètres  
 `memblock`  
 Le pointeur de bloc mémoire actuel.  
  
 `size`  
 La taille de l'allocation de mémoire  
  
 `alignment`  
 La valeur d'alignement, qui doit être une puissance entière de 2.  
  
 `offset`  
 L'offset dans l'allocation de mémoire pour forcer l'alignement.  
  
## Valeur de retour  
 `_aligned_offset_realloc` retourne un pointeur void sur le bloc mémoire realloué \(et éventuellement déplacé\).  La valeur de retour est `NULL` si la taille est de zéro et que l'argument de mémoire tampon n'est pas `NULL`, ou s'il n'y a pas assez de mémoire disponible pour développer le bloc jusqu'à la taille spécifiée.  Dans le premier cas, le bloc d'origine est libéré.  Dans le deuxième cas, le bloc d'origine reste inchangé.  Les valeur de retour pointent vers un espace de stockage, qui est garanti d'etre aligné correctement pour le stockage de n'importe quel types d'objet.  Pour obtenir un pointeur sur un type autre que void, utilisez un cast de type sur la valeur de retour.  
  
 `_aligned_offset_realloc` est marqué `__declspec(noalias)` et `__declspec(restrict)` ; cela signifie que la fonction ne modifiera pas de variables globales et que le pointeur retourné n'est pas sous la forme d'un alias.  Pour plus d'informations, consultez [noalias](../../cpp/noalias.md) et [restrict](../../cpp/restrict.md).  
  
## Notes  
 Comme [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md), `_aligned_offset_realloc` permet à une structure d'etre alignée avec un décalage à l'interieur de la structure  
  
 `_aligned_offset_realloc` est basée sur `malloc`.  Pour plus d'informations sur l'utilisation de `_aligned_offset_malloc`, consultez [](../../c-runtime-library/reference/malloc.md "malloc").  Si `memblock` est `NULL`, la fonction appelle `_aligned_offset_malloc` en interne.  
  
 Cette fonction alloue à `errno` la valeur `ENOMEM` si l'allocation de mémoire a échoué ou si la taille demandée est supérieure à `_HEAP_MAXREQ`.  Pour plus d'informations sur `errno`, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  Aussi, `_aligned_offset_realloc` valide ses paramètres.  Si `alignment` n'est pas une puissance de 2 ou si `offset` est supérieur ou égal à `size` et une valeur différente de zéro, cette fonction appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction renvoie `NULL` et définit `errno` avec la valeur `EINVAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_aligned_offset_realloc`|\<malloc.h\>|  
  
## Exemple  
 Pour plus d'informations, consultez [aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md).  
  
## Voir aussi  
 [Alignement des données](../../c-runtime-library/data-alignment.md)