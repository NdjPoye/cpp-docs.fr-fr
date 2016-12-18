---
title: "_set_new_handler | Microsoft Docs"
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
  - "_set_new_handler"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_new_handler"
  - "set_new_handler"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_new_handler (fonction)"
  - "gestion des erreurs"
  - "set_new_handler (fonction)"
  - "transfert du contrôle au gestionnaire d'erreurs"
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_new_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Transfère le contrôle à votre mécanisme de gestion des erreurs si l'opérateur `new` n'allouent pas la mémoire.  
  
## Syntaxe  
  
```  
_PNH _set_new_handler(  
   _PNH pNewHandler   
);  
```  
  
#### Paramètres  
 `pNewHandler`  
 Pointeur vers la fonction fournie par l'application de gestion de mémoire.  Un argument de 0 provoque le gestionnaire à supprimer.  
  
## Valeur de retour  
 Retourne un pointeur vers la fonction de traduction précédente d'arrêt indiquée par `_set_new_handler` afin que la fonction précédente puisse être restaurée plus tard.  Si aucune fonction n'est définie, la valeur de retour peut être utilisée pour restaurer le comportement par défaut ; cette valeur peut être NULL.  
  
## Notes  
 La fonction C\+\+ `_set_new_handler` spécifie une fonction de gestion des exceptions que les gains de contrôler si l'opérateur d'`new` n'alloue pas de mémoire.  Si `new` échoue, le système d'exécution appelle automatiquement la fonction de gestion des exceptions qui a été passée comme argument de `_set_new_handler`.  `_PNH`, défini dans New.h, pointeur vers une fonction qui retourne `int` type et accepte un argument du type `size_t`.  Utilisez `size_t` pour spécifier la quantité d'espace à allouer.  
  
 Il n'y a pas de handler par défaut.  
  
 `_set_new_handler` est essentiellement un schéma du garbage collection.  Le système d'exécution effectue l'allocation chaque fois que la fonction retourne une valeur différente de zéro et échoue si votre fonction renvoie 0.  
  
 Une occurrence de la fonction `_set_new_handler` dans enregistre de programme que la fonction de gestion des exceptions spécifié dans la liste d'arguments avec le système d'exécution :  
  
```  
#include <new.h>  
int handle_program_memory_depletion( size_t )  
{  
   // Your code  
}  
int main( void )  
{  
   _set_new_handler( handle_program_memory_depletion );  
   int *pi = new int[BIG_NUMBER];  
}  
```  
  
 Vous pouvez enregistrer l'adresse de fonction qui a reçu la dernière transmise à la fonction `_set_new_handler` et le reprendre ultérieurement :  
  
```  
_PNH old_handler = _set_new_handler( my_handler );  
   // Code that requires my_handler  
   _set_new_handler( old_handler )  
   // Code that requires old_handler  
```  
  
 La fonction C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) définit le nouveau mode de gestionnaire pour [malloc](../../c-runtime-library/reference/malloc.md).  Le nouveau mode de gestionnaire indique si, en cas de échec, `malloc` doit appeler la nouvelle routine du gestionnaire comme définit par `_set_new_handler`.  Par défaut, `malloc` n'appelle pas la nouvelle routine de gestionnaire en cas de défaillance pour allouer de la mémoire.  Vous pouvez substituer ce comportement par défaut afin que, lorsque `malloc` ne réussit pas à allouer la mémoire, `malloc` appelle la nouvelle routine de gestionnaire de la même manière que l'opérateur `new` lorsqu'il échoue pour la même raison.  Pour substituer la valeur par défaut, appelez:  
  
```  
_set_new_mode(1)  
```  
  
 tôt dans votre programme, ou créez un lien avec Newmode.obj.  
  
 Si `operator new`défini par l'utilisateur est fourni, les nouvelles fonctionnalités et ne sont pas automatiquement invité échec.  
  
 Pour plus d'informations, consultez [new](../../cpp/new-operator-cpp.md) et [delete](../../cpp/delete-operator-cpp.md) dans le *Guide de référence du langage C\+\+*.  
  
 Il existe un seul gestionnaire `_set_new_handler` pour toutes les DLL ou exécutables dynamiquement liés ; même si vous appelez `_set_new_handler` votre gestionnaire peut être remplacé par un autre ou que vous remplacez un set de gestionnaire par une DLL ou un exécutable différent.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_set_new_handler`|\<new.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Dans cet exemple, lorsque l'allocation échoue, le contrôle est transféré à MyNewHandler.  L'argument passé à MyNewHandler est le nombre d'octets demandés.  La valeur retournée de MyNewHandler est un indicateur qui indique si l'allocation doit être réexécutée : une valeur autre que zéro indique que l'allocation doit être réexécutée, une valeur zéro indique que l'allocation a échoué.  
  
```  
// crt_set_new_handler.cpp  
// compile with: /c  
#include <stdio.h>  
#include <new.h>  
#define BIG_NUMBER 0x1fffffff  
  
int coalesced = 0;  
  
int CoalesceHeap()  
{  
   coalesced = 1;  // Flag RecurseAlloc to stop   
   // do some work to free memory  
   return 0;  
}  
// Define a function to be called if new fails to allocate memory.  
int MyNewHandler( size_t size )  
{  
   printf("Allocation failed. Coalescing heap.\n");  
  
   // Call a function to recover some heap space.  
   return CoalesceHeap();  
}  
  
int RecurseAlloc() {  
   int *pi = new int[BIG_NUMBER];  
   if (!coalesced)  
      RecurseAlloc();  
   return 0;  
}  
  
int main()  
{  
   // Set the failure handler for new to be MyNewHandler.  
   _set_new_handler( MyNewHandler );  
   RecurseAlloc();  
}  
```  
  
  **Allocation a échoué.  Fusionner le segment.**  
**Cette application avait demandé le runtime afin de terminer son exécution de manière inhabituelle.**  
**Veuillez contacter l'équipe du support technique de l'application pour plus d'informations.**    
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)