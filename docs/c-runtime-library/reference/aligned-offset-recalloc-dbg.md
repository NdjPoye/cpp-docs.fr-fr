---
title: "_aligned_offset_recalloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_offset_recalloc_dbg"
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
apitype: "DLLExport"
f1_keywords: 
  - "aligned_offset_recalloc_dbg"
  - "_aligned_offset_recalloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_offset_recalloc_dbg (fonction)"
  - "aligned_offset_recalloc_dbg (fonction)"
ms.assetid: 7ab719c3-77e0-4d2e-934f-01529d062fbf
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_offset_recalloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Modifie la taille d'un bloc de mémoire qui a été alloué avec [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) ou [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) et initialise la mémoire à 0 \(version de débogage uniquement\).  
  
## Syntaxe  
  
```  
void * _aligned_offset_recalloc_dbg(    void *memblock,     size_t num,     size_t size,     size_t alignment,    size_t offset,    const char *filename,    int linenumber );  
```  
  
#### Paramètres  
 \[in\] `memblock`  
 Pointeur de bloc de mémoire actif.  
  
 \[in\] `num`  
 Nombre d'éléments.  
  
 \[in\] `size`  
 Longueur en octets de chaque élément.  
  
 \[in\] `alignment`  
 Valeur d'alignement, qui doit être un entier à puissance 2.  
  
 \[in\] `offset`  
 Décalage dans l'allocation de mémoire pour forcer l'alignement.  
  
 \[in\] `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération `realloc` ou NULL.  
  
 \[in\] `linenumber`  
 Numéro de ligne dans le fichier source où l'opération `realloc` a été demandée ou NULL.  
  
## Valeur de retour  
 `_aligned_offset_recalloc_dbg` retourne un pointeur vide vers le bloc de mémoire réalloué \(et éventuellement déplacé\).  La valeur de retour est `NULL` si la taille est égale à zéro et l'argument de mémoire tampon n'est pas `NULL`, ou si la mémoire disponible est insuffisante pour étendre le bloc à la taille donnée.  Dans le premier cas, le bloc d'origine est libéré.  Dans le second cas, le bloc d'origine est inchangé.  La valeur de retour pointe vers un espace de stockage qui est obligatoirement aligné correctement pour le stockage de tout type d'objet.  Pour obtenir un pointeur vers un type autre que void, utilisez un cast de type sur la valeur de retour.  
  
## Notes  
 `_aligned_offset_realloc_dbg` est une version de débogage de la fonction [\_aligned\_offset\_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md).  Quand [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, chaque appel à `_aligned_offset_recalloc_dbg` est réduit à un appel à \_`aligned_offset_recalloc`.  \_`aligned_offset_recalloc` et `_aligned_offset_recalloc_dbg` réallouent toutes deux un bloc de mémoire dans le tas de base, mais `_aligned_offset_recalloc_dbg` gère plusieurs fonctionnalités de débogage : des mémoires tampons de chaque côté de la partie utilisateur du bloc pour vérifier la présence de fuites, un paramètre de type de bloc pour effectuer le suivi de types d'allocation spécifiques et des informations `filename`\/`linenumber` pour déterminer l'origine des demandes d'allocation.  
  
 `_aligned_offset_realloc_dbg` réalloue le bloc de mémoire spécifié avec un peu plus d'espace que la valeur `newSize` demandée.  `newSize` peut être inférieure ou supérieure à la taille du bloc de mémoire alloué initialement.  L'espace supplémentaire est utilisé par le gestionnaire de tas de débogage pour lier les blocs de mémoire de débogage et pour fournir à l'application des informations sur les en\-têtes de débogage et les mémoires tampons de remplacement.  La réallocation peut entraîner un déplacement du bloc de mémoire initial vers un autre emplacement dans le tas, ainsi qu'une modification de la taille du bloc de mémoire.  Si le bloc de mémoire est déplacé, son contenu d'origine est remplacé.  
  
 Cette fonction affecte à `errno` la valeur `ENOMEM` si l'allocation de mémoire a échoué ou si la taille demandée \(`num` \* `size`\) était supérieure à `_HEAP_MAXREQ`.  Pour plus d'informations sur `errno`, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  De plus, `_aligned_offset_recalloc_dbg` valide ses paramètres.  Si `alignment` n'est pas une puissance de 2 ou si `offset` est supérieur ou égal à la taille demandée et différent de zéro, cette fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction retourne `NULL` et affecte à `errno` la valeur `EINVAL`.  
  
 Pour plus d'informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, voir [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Pour plus d'informations sur les types de blocs d'allocation et sur leur utilisation, voir [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Pour plus d'informations sur les différences entre l'appel à une fonction de tas standard et sa version de débogage dans une build de débogage d'une application, voir [Versions Debug des fonctions d'allocation du tas](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_aligned_offset_recalloc_dbg`|\<malloc.h\>|  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Alignement des données](../../c-runtime-library/data-alignment.md)