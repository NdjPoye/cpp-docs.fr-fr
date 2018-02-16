---
title: _set_new_handler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _set_new_handler
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_new_handler
- set_new_handler
dev_langs:
- C++
helpviewer_keywords:
- _set_new_handler function
- set_new_handler function
- error handling
- transferring control to error handler
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d82d37e13e941f98d51f2f171b9fb6f1b8071058
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="setnewhandler"></a>_set_new_handler
Transfère le contrôle à votre mécanisme de gestion des erreurs si l'opérateur `new` ne peut pas allouer de mémoire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_PNH _set_new_handler(  
   _PNH pNewHandler   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pNewHandler`  
 Pointeur vers la fonction de gestion de la mémoire fournie par l'application. L’argument 0 provoque la suppression du nouveau gestionnaire.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers la précédente fonction de gestion des exceptions enregistrée par `_set_new_handler`, afin qu'elle puisse être restaurée plus tard. Si aucune fonction précédente n'a été définie, la valeur de retour peut être utilisée pour restaurer le comportement par défaut ; cette valeur peut être `NULL`.  
  
## <a name="remarks"></a>Notes  
 La fonction C++ `_set_new_handler` spécifie une fonction de gestion des exceptions qui prend le contrôle si l'opérateur `new` ne peut pas allouer de mémoire. Si `new` échoue, le système runtime appelle automatiquement la fonction de gestion des exceptions qui a été passée comme argument à `_set_new_handler`. `_PNH`, défini dans New.h, est un pointeur vers une fonction qui retourne le type `int` et accepte un argument du type `size_t`. Utilisez `size_t` pour spécifier la quantité d'espace à allouer.  
  
 Il n'existe pas de gestionnaire par défaut.  
  
 `_set_new_handler` est essentiellement un schéma du garbage collection. Le système runtime réexécute l'allocation chaque fois que la fonction retourne une valeur différente de zéro, et échoue si votre fonction retourne 0.  
  
 Une occurrence de la fonction `_set_new_handler` dans un programme enregistre la fonction de gestion des exceptions spécifiée dans la liste d'arguments avec le système runtime :  
  
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
  
 Vous pouvez enregistrer la dernière adresse de fonction passée à la fonction `_set_new_handler` et la rétablir ultérieurement :  
  
```  
_PNH old_handler = _set_new_handler( my_handler );  
   // Code that requires my_handler  
   _set_new_handler( old_handler )  
   // Code that requires old_handler  
```  
  
 La fonction C++ [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) définit le mode de nouveau gestionnaire pour [malloc](../../c-runtime-library/reference/malloc.md). Le nouveau mode de gestionnaire indique si, en cas d'échec, `malloc` doit appeler la nouvelle routine de gestionnaire, telle qu'elle est définie par `_set_new_handler`. Par défaut, `malloc` n’appelle pas la routine de nouveau gestionnaire en cas d’échec d’allocation de mémoire. Vous pouvez remplacer ce comportement par défaut de sorte que, quand _`malloc` ne parvient pas à allouer de la mémoire, `malloc` appelle la routine de nouveau gestionnaire de la même façon que l’opérateur `new` quand il échoue pour la même raison. Pour substituer la valeur par défaut, appelez :  
  
```  
_set_new_mode(1)  
```  
  
 au début de votre programme, ou créez un lien avec Newmode.obj.  
  
 Si défini par l’utilisateur `operator new` est fourni, les nouvelles fonctions de gestionnaire ne sont pas automatiquement appelées en cas d’échec.  
  
 Pour plus d’informations, voir [new](../../cpp/new-operator-cpp.md) et [delete](../../cpp/delete-operator-cpp.md) dans la *Référence du langage C++*.  
  
 Il existe un seul gestionnaire `_set_new_handler` pour tous les exécutables et DLL dynamiquement liés. Même si vous appelez `_set_new_handler`, votre gestionnaire peut être remplacé par un autre, ou vous remplacez un ensemble de gestionnaires par une autre DLL ou un autre exécutable.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_set_new_handler`|\<new.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
 Dans cet exemple, lorsque l'allocation échoue, le contrôle est transféré à MyNewHandler. L'argument passé à MyNewHandler est le nombre d'octets demandés. La valeur retournée par MyNewHandler est un indicateur qui spécifie si l'allocation doit être réexécutée : une valeur autre que zéro indique que l'allocation doit être réexécutée, une valeur zéro indique que l'allocation a échoué.  
  
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
  
```Output  
Allocation failed. Coalescing heap.  
  
This application has requested the Runtime to terminate it in an unusual way.  
Please contact the application's support team for more information.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)