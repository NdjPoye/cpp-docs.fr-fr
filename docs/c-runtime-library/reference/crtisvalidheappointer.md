---
title: _CrtIsValidHeapPointer | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtIsValidHeapPointer
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
apitype: DLLExport
f1_keywords:
- CrtlsValidHeapPointer
- _CrtIsValidHeapPointer
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsValidHeapPointer function
- CrtIsValidHeapPointer function
ms.assetid: caf597ce-1b05-4764-9f37-0197a982bec5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4f888466e0b1625f93c4e1cf66fab0bb85678094
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="crtisvalidheappointer"></a>_CrtIsValidHeapPointer
Vérifie que le pointeur spécifié se trouve dans un tas alloué par une bibliothèque Runtime C, mais pas nécessairement par la bibliothèque CRT de l'appelant. Dans les versions de la bibliothèque CRT antérieures à Visual Studio 2010, cette fonction vérifie que le pointeur spécifié se trouve dans le tas local (version debug uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      int _CrtIsValidHeapPointer(   
   const void *userData   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `userData`  
 Pointeur indiquant le début d'un bloc de mémoire alloué.  
  
## <a name="return-value"></a>Valeur de retour  
 `_CrtIsValidHeapPointer` retourne TRUE si le pointeur spécifié se trouve dans le tas partagé par toutes les instances de bibliothèque CRT. Dans les versions du CRT antérieures à Visual Studio 2010, cette fonction retourne TRUE si le pointeur spécifié se trouve dans le tas local. Dans le cas contraire, la fonction retourne FALSE.  
  
## <a name="remarks"></a>Notes  
 Nous vous déconseillons d'utiliser cette fonction. À compter de la bibliothèque CRT de Visual Studio 2010, toutes les bibliothèques CRT partagent un même tas du système d’exploitation : le *tas de processus*. La fonction `_CrtIsValidHeapPointer` indique si le pointeur a été alloué dans un tas CRT, mais pas s'il a été alloué par la bibliothèque CRT de l'appelant. Par exemple, supposons qu'un bloc a été alloué à l'aide de la version Visual Studio 2010 de la bibliothèque CRT. Si la fonction `_CrtIsValidHeapPointer` exportée par la version de Visual Studio 2012 de la bibliothèque CRT teste le pointeur, elle retourne la valeur TRUE. Ce test n'a plus d'utilité. Dans les versions de la bibliothèque CRT antérieures à Visual Studio 2010, la fonction permet de s'assurer qu'une adresse mémoire spécifique se trouve dans le tas local. Le tas local fait référence au tas créé et géré par une instance particulière de la bibliothèque Runtime C. Si une bibliothèque de liens dynamiques (DLL) contient un lien statique vers la bibliothèque Runtime, elle possède sa propre instance du tas Runtime et donc son propre tas, indépendant du tas local de l'application. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtIsValidHeapPointer` sont supprimés durant le prétraitement.  
  
 Comme cette fonction retourne TRUE ou FALSE, elle peut être passée à l’une des macros [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) pour créer un mécanisme de gestion des erreurs de débogage simple. L'exemple suivant provoque un échec d'assertion si l'adresse spécifiée n'est pas située dans le tas local :  
  
```  
_ASSERTE( _CrtIsValidHeapPointer( userData ) );  
```  
  
 Pour plus d’informations sur la façon dont `_CrtIsValidHeapPointer` peut être utilisé avec d’autres macros et fonctions de débogage, consultez [Macros pour la création de rapports](/visualstudio/debugger/macros-for-reporting). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, voir [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtIsValidHeapPointer`|\<crtdbg.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment tester la validité de la mémoire quand elle est utilisée avec des bibliothèques Runtime C antérieures à Visual Studio 2010. Cet exemple est fourni pour les utilisateurs de code de bibliothèque CRT hérité.  
  
```  
// crt_isvalid.c  
/*  
 * This program allocates a block of memory using _malloc_dbg  
 * and then tests the validity of this memory by calling   
 * _CrtIsMemoryBlock,_CrtIsValidPointer, and _CrtIsValidHeapPointer.  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
#define  TRUE   1  
#define  FALSE  0  
  
int main( void )  
{  
        char *my_pointer;  
  
        /*   
         * Call _malloc_dbg to include the filename and line number  
         * of our allocation request in the header information  
         */  
        my_pointer = (char *)_malloc_dbg( sizeof(char) * 10,   
        _NORMAL_BLOCK, __FILE__, __LINE__ );  
  
        // Ensure that the memory got allocated correctly  
        _CrtIsMemoryBlock((const void *)my_pointer, sizeof(char) * 10,   
        NULL, NULL, NULL );  
  
         // Test for read/write accessibility  
        if (_CrtIsValidPointer((const void *)my_pointer,   
        sizeof(char) * 10, TRUE))  
                printf("my_pointer has read and write accessibility.\n");  
        else  
                printf("my_pointer only has read access.\n");  
  
        // Make sure my_pointer is within the local heap  
        if (_CrtIsValidHeapPointer((const void *)my_pointer))  
                printf("my_pointer is within the local heap.\n");  
        else  
                printf("my_pointer is not located within the local"  
                       " heap.\n");  
  
        free(my_pointer);  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
my_pointer has read and write accessibility.  
my_pointer is within the local heap.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)