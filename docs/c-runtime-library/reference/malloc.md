---
title: "malloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "malloc"
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
  - "malloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "malloc (fonction)"
  - "allocation de mémoire"
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# malloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Alloue les blocs de mémoire.  
  
## Syntaxe  
  
```  
void *malloc(  
   size_t size   
);  
```  
  
#### Paramètres  
 `size`  
 Octets à allouer.  
  
## Valeur de retour  
 `malloc` retourne un pointeur void vers l'espace alloué, ou `NULL` si la mémoire disponible est insuffisante.  Pour rétablir un pointeur sur un type autre qu'un `void`, utilisez un cast de type sur la valeur de retour.  L'espace de stockage sur lequel pointe la valeur de retour est obligatoirement aligné pour le stockage de tout type d'objet qui a une spécification d'alignement inférieure ou égale à celui de l'alignement simple. \(Dans Visual C\+\+, l'alignement simple est l'alignement requis pour un `double`, ou 8 octets.  Dans le code qui cible les plateformes 64 bits, il correspond à 16 octets.\) Utilisez [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) pour allouer un stockage pour les objets qui ont une plus grande spécification d'alignement \(par exemple, les types de SSE [\_\_m128](../../cpp/m128.md) et `__m256`, et les types qui sont déclarés à l'aide de `__declspec(align(``n``))` où `n` est supérieur à 8.  Si `size` a la valeur 0, `malloc` alloue un élément de longueur zéro dans le tas et retourne un pointeur valide à cet élément.  Vérifiez toujours le retour de `malloc`, même si la quantité de mémoire demandée est faible.  
  
## Notes  
 La fonction `malloc` alloue un bloc de mémoire d'au moins `size` octets.  Le bloc peut être plus grand que `size` octets en raison de l'espace requis pour les informations d'alignement et de maintenance.  
  
 `malloc` affecte à `errno` la valeur `ENOMEM` si une allocation de mémoire échoue ou si la quantité de mémoire demandée dépasse `_HEAP_MAXREQ`.  Pour plus d'informations sur ces codes de retour et autres, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Le code de démarrage utilise `malloc` pour allouer un stockage pour les variables `_environ`, `envp` et `argv`.  Les fonctions suivantes et leurs équivalents à caractère élargi appellent également `malloc`.  
  
|||||  
|-|-|-|-|  
|[calloc](../../c-runtime-library/reference/calloc.md)|[fscanf](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[\_getw](../../c-runtime-library/reference/getw.md)|[setvbuf](../../c-runtime-library/reference/setvbuf.md)|  
|[fonctions de \_exec](../../c-runtime-library/exec-wexec-functions.md)|[fseek](../../c-runtime-library/reference/fseek-fseeki64.md)|[\_popen](../../c-runtime-library/reference/popen-wpopen.md)|[fonctions de \_spawn](../../c-runtime-library/spawn-wspawn-functions.md)|  
|[fgetc](../../c-runtime-library/reference/fgetc-fgetwc.md)|[fsetpos](../../c-runtime-library/reference/fsetpos.md)|[printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[\_strdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)|  
|[\_fgetchar](../../c-runtime-library/reference/fgetc-fgetwc.md)|[\_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[putc](../../c-runtime-library/reference/putc-putwc.md)|[système](../../c-runtime-library/reference/system-wsystem.md)|  
|[fgets](../../c-runtime-library/reference/fgets-fgetws.md)|[fwrite](../../c-runtime-library/reference/fwrite.md)|[putchar](../../c-runtime-library/reference/putc-putwc.md)|[\_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](../../c-runtime-library/reference/getc-getwc.md)|[\_putenv](../../c-runtime-library/reference/putenv-wputenv.md)|[ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md)|  
|[fputc](../../c-runtime-library/reference/fputc-fputwc.md)|[getchar](../../c-runtime-library/reference/getc-getwc.md)|[puts](../../c-runtime-library/reference/puts-putws.md)|[vfprintf](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[\_fputchar](../../c-runtime-library/reference/fputc-fputwc.md)|[\_getcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[\_putw](../../c-runtime-library/reference/putw.md)|[vprintf](../../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|  
|[fputs](../../c-runtime-library/reference/fputs-fputws.md)|[\_getdcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)||  
|[fread](../../c-runtime-library/reference/fread.md)|[obtient](../../c-runtime-library/gets-getws.md)|[\_searchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)||  
  
 La fonction C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) définit le nouveau mode de gestionnaire pour `malloc`.  Le nouveau mode de gestionnaire indique si, en cas de échec, `malloc` doit appeler la nouvelle routine du gestionnaire comme définit par [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md).  Par défaut, `malloc` n'appelle pas la nouvelle routine de gestionnaire en cas de défaillance pour allouer de la mémoire.  Vous pouvez substituer ce comportement par défaut afin que, lorsque `malloc` ne réussit pas à allouer la mémoire, `malloc` appelle la nouvelle routine de gestionnaire de la même manière que l'opérateur `new` lorsqu'il échoue pour la même raison.  Pour substituer la valeur par défaut, appelez  
  
```cpp  
_set_new_mode(1)  
```  
  
 tôt dans votre programme, ou créez un lien avec NEWMODE.OBJ \(consultez [Options de lien](../../c-runtime-library/link-options.md)\).  
  
 Lorsque l'application est liée à une version debug des bibliothèques Runtime C, `malloc` est résolu en [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  Pour plus d'informations sur la gestion du tas pendant le processus de débogage, consultez [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `malloc` est marqué `__declspec(noalias)` et `__declspec(restrict)` ; cela signifie que la fonction n'est pas garantie pour modifier les variables globales, et que le pointeur retourné n'est pas un alias.  Pour plus d’informations, consultez [noalias](../../cpp/noalias.md) et [restrict](../../cpp/restrict.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`malloc`|\<stdlib.h\> et \<malloc.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```c  
// crt_malloc.c  
// This program allocates memory with  
// malloc, then frees the memory with free.  
  
#include <stdlib.h>   // For _MAX_PATH definition  
#include <stdio.h>  
#include <malloc.h>  
  
int main( void )  
{  
   char *string;  
  
   // Allocate space for a path name  
   string = malloc( _MAX_PATH );  
  
   // In a C++ file, explicitly cast malloc's return.  For example,   
   // string = (char *)malloc( _MAX_PATH );  
  
   if( string == NULL )  
      printf( "Insufficient memory available\n" );  
   else  
   {  
      printf( "Memory space allocated for path name\n" );  
      free( string );  
      printf( "Memory freed\n" );  
   }  
}  
```  
  
  **Espace mémoire alloué pour le nom du chemin d'accès**  
**Mémoire libérée**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md)