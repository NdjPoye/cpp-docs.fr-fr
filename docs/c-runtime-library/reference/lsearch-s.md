---
title: "_lsearch_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lsearch_s"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_lsearch_s"
  - "lsearch_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_lsearch_s (fonction)"
  - "tableaux (CRT), rechercher"
  - "clés, rechercher dans les tableaux"
  - "recherche linéaire"
  - "lsearch_s (fonction)"
  - "rechercher, linéaires"
  - "valeurs, rechercher"
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _lsearch_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Effectue une recherche linéaire sur la valeur.  Il s'agit de versions de [\_lsearch](../../c-runtime-library/reference/lsearch.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
void *_lsearch_s(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### Paramètres  
 `key`  
 Objet  à rechercher.  
  
 `base`  
 Pointeur vers la base de la table à rechercher.  
  
 `num`  
 Nombre d'éléments  
  
 `size`  
 Taille de chaque élément du tableau en octets.  
  
 `compare`  
 Pointeur vers la routine de comparaison.  Le deuxième paramètre est un pointeur vers la clé pour la recherche.  Le troisième paramètre est un pointeur vers un élément de tableau à comparer à la clé.  
  
 `context`  
 Un pointeur vers un objet, qui peut être accessible dans la fonction de comparaison.  
  
## Valeur de retour  
 Si `key` est trouvé, `_lsearch_s` retourne un pointeur vers l'élément du tableau à la `base` qui correspond à `key`.  Si `key` est introuvable, `_lsearch_s` retourne un pointeur sur l'élément récemment ajouté à la fin du tableau.  
  
 Si des paramètres non valides sont transmis à la fonction, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno`  avec la valeur `EINVAL` et retournent `NULL`.  Pour plus d'informations, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### Conditions d'erreur  
  
|`key`|`base`|`compare`|`num`|`size`|`errno`|  
|-----------|------------|---------------|-----------|------------|-------------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|\!\= 0|any|`EINVAL`|  
|any|any|any|any|zéro|`EINVAL`|  
|any|any|`NULL`|Un|any|`EINVAL`|  
  
## Notes  
 La fonction `_lsearch_s` effectue une recherche séquentielle pour la valeur `key` dans un tableau d'éléments de `num`éléments, chacun de`width`octets.  Contrairement à `bsearch_s`, `_lsearch_s` ne nécessite pas que le tableau soit trié.  Si `key` est introuvable, alors `_lsearch_s` l'ajoute à la fin de la table et incrémente `num`.  
  
 La fonction `compare` est un pointeur à une routine fournie à l'utilisateur qui compare deux éléments de tableau et retourne une valeur qui spécifie leur relation.  La fonction `compare` prend également le pointeur au contexte comme premier argument.  `_lsearch_s` appelle `compare` à une ou plusieurs reprises lors de la recherche, en passant des pointeurs vers deux éléments de tableau à chaque appel.  `compare` doit comparer les éléments puis retourner ou une valeur différente de zéro \(c'est\-à\-dire que les éléments sont différents\) ou 0 \(ce qui signifie les éléments sont identiques\).  
  
 Le pointeur de `context` peut être utile si la structure de données est fait partie d'un objet et que la fonction `compare` doit accéder à des membres de l'objet.  Par exemple, le code de la fonction `compare` peut convertir le pointeur void au type objet approprié et accéder aux membres de cet objet.  L'ajout du pointeur `context` permet de rendre`_lsearch_s` plus sécurisé car le contexte supplémentaire peut être utilisé pour éviter les bogues de reentrées associés à l'utilisation des variables statiques pour rendre les données disponibles à la fonction `compare`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_lsearch_s`|\<Rechercher\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Recherche et tri](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md)   
 [\_lfind\_s](../../c-runtime-library/reference/lfind-s.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)