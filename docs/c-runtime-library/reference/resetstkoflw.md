---
title: _resetstkoflw | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _resetstkoflw
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
- resetstkoflw
- _resetstkoflw
dev_langs:
- C++
helpviewer_keywords:
- resetstkoflw function
- stack overflow
- stack, recovering
- _resetstkoflw function
ms.assetid: 319529cd-4306-4d22-810b-2063f3ad9e14
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 16d166f205f026977673e39bd539b377496bdc0c
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="resetstkoflw"></a>_resetstkoflw
Récupère d'un dépassement de capacité de la pile.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
int _resetstkoflw ( void );  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro si la fonction réussit, zéro si elle échoue.  
  
## <a name="remarks"></a>Notes  
 La fonction `_resetstkoflw` récupère d’une condition de dépassement de capacité de la pile, ce qui permet à un programme de poursuivre son exécution au lieu d’échouer avec une erreur d’exception fatale. Si la fonction `_resetstkoflw` n'est pas appelée, aucune page de garde n'est créée après la précédente exception. La prochaine fois qu’un dépassement de capacité de la pile se produit, aucune exception n’est déclarée et le processus s’achève sans avertissement.  
  
 Si un thread au sein d’une application provoque une exception **EXCEPTION_STACK_OVERFLOW**, cela signifie que le thread a quitté sa pile dans un état endommagé. Cette exception se distingue d’autres exceptions, telles que **EXCEPTION_ACCESS_VIOLATION** ou **EXCEPTION_INT_DIVIDE_BY_ZERO**, où la pile n’est pas endommagée. La pile est définie sur une valeur arbitrairement petite lorsque le programme est chargé pour la première fois. La pile se développe ensuite à la demande pour répondre aux besoins du thread. Cela est implémenté en plaçant une page avec un accès par PAGE_GUARD à la fin de la pile actuelle. Pour plus d’informations, consultez [Création de pages de garde](http://msdn.microsoft.com/library/windows/desktop/aa366549).  
  
 Lorsque le code fait pointer le pointeur de pile vers une adresse sur cette page, une exception se produit et le système exécute les trois actions suivantes :  
  
-   Supprime la protection PAGE_GUARD sur la page de garde afin que le thread puisse lire et écrire des données dans la mémoire.  
  
-   Alloue une nouvelle page de garde située une page en dessous de la dernière.  
  
-   Réexécute l'instruction qui a déclenché l'exception.  
  
 Ainsi, le système peut augmenter automatiquement la taille de la pile pour le thread. Chaque thread d'un processus a une taille de pile maximale. La taille de la pile est définie au moment de la compilation par l’instruction [/STACK (Allocations de piles)](../../build/reference/stack-stack-allocations.md) ou par l’instruction [STACKSIZE](../../build/reference/stacksize.md) dans le fichier .def du projet.  
  
 Lorsque cette taille de pile maximale est dépassée, le système exécute les trois actions suivantes :  
  
-   Supprime la protection PAGE_GUARD sur la page de garde, comme décrit précédemment.  
  
-   Essaie d'allouer une nouvelle page de garde en dessous de la dernière. Toutefois, cela échoue car la taille de pile maximale a été dépassée.  
  
-   Lève une exception afin que le thread puisse la gérer dans le bloc d'exception.  
  
 Notez que, à ce stade, la pile ne contient plus de page de garde. La prochaine fois que le programme augmentera la pile jusqu'à la fin, où devra se trouver une page de garde, il écrira au-delà de la fin de la pile et provoquera une violation d'accès.  
  
 Appelez `_resetstkoflw` pour rétablir la page de garde chaque fois qu'une récupération est effectuée après une exception de dépassement de capacité de la pile. Cette fonction peut être appelée de l’intérieur du corps principal d’un bloc `__except` ou de l’extérieur d’un bloc **__except**. Toutefois, il existe quelques restrictions sur son utilisation. La fonction `_resetstkoflw` ne doit jamais être appelée depuis :  
  
-   Une expression de filtre.  
  
-   Une fonction de filtre.  
  
-   Une fonction appelée à partir d'une fonction de filtre.  
  
-   Un bloc **catch**.  
  
-   Un bloc `__finally`.  
  
 À ce stade, la pile n'est pas encore suffisamment déroulée.  
  
 Les exceptions de dépassement de la capacité de la pile sont générées comme des exceptions structurées, pas comme des exceptions C++, si bien que la fonction `_resetstkoflw` n’est pas utile dans un bloc **catch** ordinaire, car elle n’intercepte pas d’exception de dépassement de la capacité de la pile. Toutefois, si [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) est utilisé pour implémenter un traducteur d’exceptions structurées qui lève des exceptions C++ (comme dans le deuxième exemple), une exception de dépassement de la capacité de la pile provoque une exception C++ qui peut être gérée par le bloc catch C++.  
  
 Il est déconseillé d’appeler **_resetstkoflw** dans un bloc catch C++ qui est atteint à partir d’une exception levée par la fonction de traduction d’exceptions structurées. Dans ce cas, l'espace de la pile n'est pas libéré et le pointeur de pile n'est pas réinitialisé jusqu'à l'extérieur du bloc catch, même si des destructeurs ont été appelés pour les objets destructibles avant le bloc catch. Cette fonction ne doit pas être appelée jusqu'à ce que l'espace de la pile soit libéré et que le pointeur de pile ait été réinitialisé. Par conséquent, elle doit être appelée uniquement après avoir quitté le bloc catch. Un espace de pile limité doit être utilisé dans le bloc catch, car un dépassement de capacité de la pile qui se produit dans le bloc catch qui tente lui-même de récupérer d'un précédent dépassement de capacité de la pile n'est pas récupérable et peut empêcher le programme de répondre lorsque le dépassement de capacité dans le bloc catch lève une exception qui est elle-même gérée par le même bloc catch.  
  
 Dans certaines situations, la fonction **_resetstkoflw** peut échouer même si elle est utilisée dans un emplacement approprié, comme dans un bloc **__except**. Si, même après avoir déroulé la pile, il ne reste pas assez d’espace de pile pour exécuter **_resetstkoflw** sans écrire dans la dernière page de la pile, **_resetstkoflw** ne peut pas réinitialiser la dernière page de la pile en tant que page de garde et retourne 0, ce qui indique un échec. Par conséquent, l'utilisation sécurisée de cette fonction doit inclure la vérification de la valeur de retour au lieu de supposer que l'utilisation de la pile ne présente aucun risque.  
  
 Gestion structurée des exceptions n’intercepte pas un `STATUS_STACK_OVERFLOW` exception lors de l’application est compilée avec `/clr` (consultez [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md)).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_resetstkoflw`|\<malloc.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
 **Bibliothèques :** toutes les versions des [fonctionnalités de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
 L'exemple de code suivant montre l'utilisation recommandée de la fonction `_resetstkoflw`.  
  
```  
// crt_resetstkoflw.c  
// Launch program with and without arguments to observe  
// the difference made by calling _resetstkoflw.  
  
#include <malloc.h>  
#include <stdio.h>  
#include <windows.h>  
  
void recursive(int recurse)  
{  
   _alloca(2000);  
   if (recurse)  
      recursive(recurse);  
}  
  
// Filter for the stack overflow exception.  
// This function traps the stack overflow exception, but passes  
// all other exceptions through.   
int stack_overflow_exception_filter(int exception_code)  
{  
   if (exception_code == EXCEPTION_STACK_OVERFLOW)  
   {  
       // Do not call _resetstkoflw here, because  
       // at this point, the stack is not yet unwound.  
       // Instead, signal that the handler (the __except block)  
       // is to be executed.  
       return EXCEPTION_EXECUTE_HANDLER;  
   }  
   else  
       return EXCEPTION_CONTINUE_SEARCH;  
}  
  
int main(int ac)  
{  
   int i = 0;  
   int recurse = 1, result = 0;  
  
   for (i = 0 ; i < 10 ; i++)  
   {  
      printf("loop #%d\n", i + 1);  
      __try  
      {  
         recursive(recurse);  
  
      }  
  
      __except(stack_overflow_exception_filter(GetExceptionCode()))  
      {  
         // Here, it is safe to reset the stack.  
  
         if (ac >= 2)  
         {  
            puts("resetting stack overflow");  
            result = _resetstkoflw();  
         }  
      }  
  
      // Terminate if _resetstkoflw failed (returned 0)  
      if (!result)  
         return 3;  
   }  
  
   return 0;  
}  
```  
  
## <a name="sample-output"></a>Résultat de l'exemple  
 Sans arguments de programme :  
  
```  
loop #1  
```  
  
 Le programme cesse de répondre sans exécuter d'autres itérations.  
  
 Avec des arguments de programme :  
  
```  
loop #1  
resetting stack overflow  
loop #2  
resetting stack overflow  
loop #3  
resetting stack overflow  
loop #4  
resetting stack overflow  
loop #5  
resetting stack overflow  
loop #6  
resetting stack overflow  
loop #7  
resetting stack overflow  
loop #8  
resetting stack overflow  
loop #9  
resetting stack overflow  
loop #10  
resetting stack overflow  
```  
  
### <a name="description"></a>Description  
 L'exemple suivant illustre l'utilisation recommandée de `_resetstkoflw` dans un programme où les exceptions structurées sont converties en exceptions C++.  
  
### <a name="code"></a>Code  
  
```  
// crt_resetstkoflw2.cpp  
// compile with: /EHa  
// _set_se_translator requires the use of /EHa  
#include <malloc.h>  
#include <stdio.h>  
#include <windows.h>  
#include <eh.h>  
  
class Exception { };  
  
class StackOverflowException : Exception { };  
  
// Because the overflow is deliberate, disable the warning that  
// this function will cause a stack overflow.  
#pragma warning (disable: 4717)  
void CauseStackOverflow (int i)  
{  
        // Overflow the stack by allocating a large stack-based array  
        // in a recursive function.  
        int a[10000];  
        printf("%d ", i);  
        CauseStackOverflow (i + 1);  
}  
  
void __cdecl SEHTranslator (unsigned int code, _EXCEPTION_POINTERS*)  
{  
   // For stack overflow exceptions, throw our own C++   
   // exception object.  
   // For all other exceptions, throw a generic exception object.  
   // Use minimal stack space in this function.  
   // Do not call _resetstkoflw in this function.  
  
   if (code == EXCEPTION_STACK_OVERFLOW)  
      throw StackOverflowException ( );  
   else  
      throw Exception( );  
}  
  
int main ( )  
{  
        bool stack_reset = false;  
        bool result = false;  
  
        // Set up a function to handle all structured exceptions,  
        // including stack overflow exceptions.  
        _set_se_translator (SEHTranslator);  
  
        try  
        {  
            CauseStackOverflow (0);  
        }  
        catch (StackOverflowException except)  
        {  
                // Use minimal stack space here.  
                // Do not call _resetstkoflw here.  
                printf("\nStack overflow!\n");  
                stack_reset = true;  
        }  
        catch (Exception except)  
        {  
                // Do not call _resetstkoflw here.  
                printf("\nUnknown Exception!\n");  
        }  
        if (stack_reset)  
        {  
          result = _resetstkoflw();  
          // If stack reset failed, terminate the application.  
          if (result == 0)  
             exit(1);  
        }  
  
        void* pv = _alloca(100000);  
        printf("Recovered from stack overflow and allocated 100,000 bytes"  
               " using _alloca.");  
  
   return 0;  
}  
```  
  
## <a name="sample-output"></a>Résultat de l'exemple  
  
```  
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24  
Stack overflow!  
Recovered from stack overflow and allocated 100,000 bytes using _alloca.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [_alloca](../../c-runtime-library/reference/alloca.md)
