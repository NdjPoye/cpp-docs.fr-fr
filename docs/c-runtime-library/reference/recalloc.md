---
title: "_recalloc | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_recalloc"
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
  - "_recalloc"
  - "recalloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_recalloc (fonction)"
  - "recalloc (fonction)"
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _recalloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Combinaison de `realloc` et de `calloc`.  Réaffecte un tableau en mémoire et initialise les éléments à 0.  
  
## Syntaxe  
  
```  
void *_recalloc(   
   void *memblock  
   size_t num,  
   size_t size   
);  
```  
  
#### Paramètres  
 `memblock`  
 Pointeur vers un bloc de mémoire précédemment alloué.  
  
 `num`  
 Nombre d'éléments  
  
 `size`  
 Longueur en octets de chaque élément.  
  
## Valeur de retour  
 `_recalloc` retourne un pointeur `void` sur le bloc mémoire realloué \(et éventuellement déplacé\).  
  
 S'il n'y a pas assez de mémoire pour développer le bloc à la taille spécifiée, le bloc d'origine reste inchangé, et `NULL` est retourné.  
  
 Si la taille requise est zéro, le bloc référencé par `memblock` est récupéré ; la valeur de retour est `NULL`, et `memblock` est laissé, le curseur vers un bloc libéré.  
  
 Les valeur de retour pointent vers un espace de stockage, qui est garanti d'être aligné correctement pour le stockage de n'importe quel type d'objet.  Pour obtenir un pointeur sur un type autre qu'un `void`, utilisez un cast de type sur la valeur de retour.  
  
## Notes  
 La fonction `recalloc` change la taille d'un bloc de mémoire alloué.  L'argument `memblock` pointe au début du bloc de mémoire.  Si `memblock` est `NULL`, `recalloc` se comporte de la même manière que [calloc](../../c-runtime-library/reference/calloc.md) et alloue un nouveau bloc d'octets de dimension `num`\* `size`.  Chaque élément est initialisée à 0.  Si `memblock` n'est pas `NULL`, ce doit être un pointeur retourné par un appel précédent à `calloc`,[malloc](../../c-runtime-library/reference/malloc.md), ou à [realloc](../../c-runtime-library/reference/realloc.md).  
  
 Étant donné que le nouveau bloc peut se trouver dans un emplacement de mémoire, le pointeur retourné par `recalloc` n'est pas garanti être un pointeur passé via l'argument `memblock`.  
  
 `_recalloc` affecte à `errno` la valeur `ENOMEM` si l'allocation de mémoire échoue ou si la quantité de mémoire demandée dépasse `_HEAP_MAXREQ`.  Pour plus d'informations sur ceci et sur les codes d'erreurs, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `recalloc` appelle  `realloc`[\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) pour utiliser la fonction C\+\+ pour définir le nouveau mode gestionnaire.  Le nouveau mode de gestionnaire indique si, en cas de échec, `realloc` doit appeler la nouvelle routine du gestionnaire comme définit par [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md).  Par défaut, `realloc` n'appelle pas la nouvelle routine de gestionnaire en cas de défaillance pour allouer de la mémoire.  Vous pouvez substituer ce comportement par défaut afin que, lorsque \_`recalloc` ne réussit pas à allouer la mémoire, `realloc` appelle la nouvelle routine de gestionnaire de la même manière que l'opérateur `new` lorsqu'il échoue pour la même raison.  Pour substituer la valeur par défaut, appelez  
  
```  
_set_new_mode(1)  
```  
  
 tôt dans votre programme, ou créez un lien avec NEWMODE.OBJ \(consultez \).  
  
 Lorsque l'application est liée à une version debug des bibliothèques Runtime C, `recalloc` est résolu en [\_recalloc\_dbg](../../c-runtime-library/reference/recalloc-dbg.md).  Pour plus d'informations sur la gestion du tas pendant le processus de débogage, consultez [The CRT Debug Heap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `_recalloc` est marqué `__declspec(noalias)` et `__declspec(restrict)` ; cela signifie que la fonction ne modifiera pas de variables globales et que le pointeur retourné n'est pas sous la forme d'un alias.  Pour plus d'informations, consultez [noalias](../../cpp/noalias.md) et [restrict](../../cpp/restrict.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_recalloc`|\<stdlib.h\> et \<malloc.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [\_recalloc\_dbg](../../c-runtime-library/reference/recalloc-dbg.md)   
 [\_aligned\_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)   
 [\_aligned\_offset\_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [Options de lien](../../c-runtime-library/link-options.md)