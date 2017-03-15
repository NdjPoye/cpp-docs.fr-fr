---
title: "memcpy, wmemcpy | Microsoft Docs"
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
  - "memcpy"
  - "wmemcpy"
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
  - "wmemcpy"
  - "memcpy"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "memcpy (fonction)"
  - "wmemcpy (fonction)"
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# memcpy, wmemcpy
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Copie des octets entre les mémoires tampon.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez  [memcpy\_s, wmemcpy\_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md).  
  
## Syntaxe  
  
```  
void *memcpy(  
   void *dest,  
   const void *src,  
   size_t count   
);  
wchar_t *wmemcpy(  
   wchar_t *dest,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### Paramètres  
 `dest`  
 Nouvelle mémoire tampon.  
  
 `src`  
 Mémoire tampon à partir de laquelle effectuer la copie.  
  
 `count`  
 Nombre de caractères à copier.  
  
## Valeur de retour  
 la valeur de la propriété `dest` ;  
  
## Notes  
 `memcpy` copie `count` octets de `src` vers `dest` ; `wmemcpy` copie `count` caractères larges \(sur deux octets\).  Si la source et la destination se chevauchent, le comportement de `memcpy` n'est pas défini.  Utilisez `memmove` pour gérer les régions qui se chevauchent.  
  
> [!IMPORTANT]
>  Assurez\-vous que la mémoire tampon de destination est d'une taille identique ou supérieure à celle de la mémoire tampon source.  Pour plus d'informations, voir [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
> [!IMPORTANT]
>  Étant donné que pour de très nombreux dépassements de mémoire tampon, et donc de failles de sécurité potentielles, une utilisation incorrecte de `memcpy` a été détectée, cette fonction est répertoriée parmi les fonctions « bannies » par le cycle SDL \(Security Development Lifecycle\).  Vous pouvez remarquer que certaines classes de bibliothèque VC\+\+ continuent à utiliser `memcpy`.  Vous pouvez même remarquer que l'optimiseur du compilateur VC\+\+ émet parfois des appels à `memcpy`.  Le produit Visual C\+\+ est développé conformément au processus SDL, et l'utilisation de cette fonction bannie a donc été évaluée avec attention.  Dans le cas de son utilisation dans des bibliothèques, les appels ont été examinés avec soin pour garantir que les dépassements de mémoire tampon ne seront pas autorisés via ces appels.  Dans le cas le compilateur, certains modèles de code sont parfois reconnus comme étant identiques au modèle de `memcpy` et ils sont donc remplacés par un appel à la fonction.  Dans ce cas, l'utilisation de `memcpy` n'est pas plus risquée que les instructions d'origine l'auraient été ; elles ont simplement été optimisées en un appel à la fonction `memcpy` optimisée pour les performances.  Tout comme l'utilisation de fonctions CRT « sécurisées » ne garantit pas la sécurité \(elles rendent simplement plus compliquée une utilisation risquée\), l'utilisation de fonctions « bannies » ne signifie pas qu'il y a danger à coup sûr \(elles nécessitent seulement un examen plus attentif pour garantir la sécurité\).  
>   
>  Comme l'utilisation de `memcpy` par le compilateur et les bibliothèques VC\+\+ a été examinée avec soin, ces appels sont autorisés dans du code qui est conforme à SDL.  Les appels de `memcpy` introduits dans le code source d'applications sont conformes à SDL seulement quand cette utilisation a été vérifiée par des experts en sécurité.  
  
 Les fonctions `memcpy` et `wmemcpy` seront déconseillées seulement si la constante `_CRT_SECURE_DEPRECATE_MEMORY` est définie avant l'instruction d'inclusion pour que les fonctions soient déconseillées, comme dans l'exemple ci\-dessous :  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <memory.h>  
```  
  
 ou  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <wchar.h>  
```  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`memcpy`|\<memory.h\> ou \<string.h\>|  
|`wmemcpy`|\<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez [memmove](../../c-runtime-library/reference/memmove-wmemmove.md) pour un exemple d'utilisation de `memcpy`.  
  
## Voir aussi  
 [Manipulation de la mémoire tampon](../../c-runtime-library/buffer-manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memmove, wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcpy\_s, wcscpy\_s, \_mbscpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)