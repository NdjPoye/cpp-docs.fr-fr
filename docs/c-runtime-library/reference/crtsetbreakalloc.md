---
title: _CrtSetBreakAlloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtSetBreakAlloc
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
- CrtSetBreakAlloc
- _CrtSetBreakAlloc
dev_langs:
- C++
helpviewer_keywords:
- CrtSetBreakAlloc function
- _CrtSetBreakAlloc function
ms.assetid: 33bfc6af-a9ea-405b-a29f-1c2d4d9880a1
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: a11b7847e83a129099e0f54cccce35032cf68fe4
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="crtsetbreakalloc"></a>_CrtSetBreakAlloc
Définit un point d'arrêt sur un numéro d'ordre d'allocation d'objet spécifié (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      long _CrtSetBreakAlloc(   
   long lBreakAlloc   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *lBreakAlloc*  
 Numéro d'ordre d'allocation pour lequel le point d'arrêt est défini.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le numéro d'ordre d'allocation d'objet précédent qui avait un point d'arrêt défini.  
  
## <a name="remarks"></a>Notes  
 `_CrtSetBreakAlloc` permet à une application de détecter une fuite de mémoire en s'arrêtant à un point d'allocation de mémoire spécifique et en remontant jusqu'à l'origine de la demande. La fonction utilise le numéro d'ordre d'allocation d'objet séquentiel assigné au bloc de mémoire au moment où il a été alloué dans le tas. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtSetBreakAlloc` sont supprimés durant le prétraitement.  
  
 Le numéro d’ordre d’allocation d’objet est stocké dans le champ *lRequest* de la structure **_CrtMemBlockHeader**, définie dans Crtdbg.h. Quand les informations sur un bloc de mémoire sont rapportées par l'une des fonctions de vidage du débogage, ce numéro est placé entre accolades (par exemple, « {36} »).  
  
 Pour plus d’informations sur l’utilisation de `_CrtSetBreakAlloc` avec d’autres fonctions de gestion de mémoire, voir [Tracking Heap Allocation Requests](/visualstudio/debugger/crt-debug-heap-details) (Suivi des demandes d’allocation du tas). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtSetBreakAlloc`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_setbrkal.c  
// compile with: -D_DEBUG /MTd -Od -Zi -W3 /c /link -verbose:lib -debug  
  
/*  
 * In this program, a call is made to the _CrtSetBreakAlloc routine  
 * to verify that the debugger halts program execution when it reaches  
 * a specified allocation number.  
 */  
  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( )  
{  
        long allocReqNum;  
        char *my_pointer;  
  
        /*   
         * Allocate "my_pointer" for the first  
         * time and ensure that it gets allocated correctly  
         */  
        my_pointer = malloc(10);  
        _CrtIsMemoryBlock(my_pointer, 10, &allocReqNum, NULL, NULL);  
  
        /*   
         * Set a breakpoint on the allocation request  
         * number for "my_pointer"  
         */  
        _CrtSetBreakAlloc(allocReqNum+2);  
  
        /*   
         * Alternate freeing and reallocating "my_pointer"  
         * to verify that the debugger halts program execution  
         * when it reaches the allocation request  
         */  
        free(my_pointer);  
        my_pointer = malloc(10);  
        free(my_pointer);  
        my_pointer = malloc(10);  
        free(my_pointer);  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)
