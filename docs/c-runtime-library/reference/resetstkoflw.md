---
title: "_resetstkoflw | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_resetstkoflw"
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
  - "resetstkoflw"
  - "_resetstkoflw"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_resetstkoflw (fonction)"
  - "resetstkoflw (fonction)"
  - "dépassement de capacité de la pile"
  - "pile, récupérer"
ms.assetid: 319529cd-4306-4d22-810b-2063f3ad9e14
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _resetstkoflw
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère d'un dépassement de capacité de la pile.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
  
int _resetstkoflw ( void );  
  
```  
  
## Valeur de retour  
 Valeur différente de zéro si la fonction réussit, zéro si elle échoue.  
  
## Notes  
 La fonction `_resetstkoflw` est récupérée à partir d'une condition de dépassement de capacité de la pile, en autorisant un programme à continuer au lieu d'échouer en provoquant une erreur d'exception irrécupérable.  Si la fonction `_resetstkoflw` n'est pas appelée, aucune page de garde n'est créée après la précédente exception.  Lors du prochain dépassement de capacité de la pile, aucune exception n'est levée et le processus s'achève sans avertissement.  
  
 Si un thread dans une application provoque une exception **EXCEPTION\_STACK\_OVERFLOW**, le thread a quitté sa pile dans un état endommagé.  Ceci contraste avec d'autres exceptions comme **EXCEPTION\_ACCESS\_VIOLATION** ou **EXCEPTION\_INT\_DIVIDE\_BY\_ZERO**, où la pile n'est pas endommagée.  La pile est fixé une valeur arbitrairement petite lorsque le programme est chargé pour la première fois.  La pile se développe ensuite à la demande pour répondre aux besoins du thread.  Cela est implémenté en plaçant une page avec accès par PAGE\_GUARD à la fin de la pile actuelle.  Pour plus d'informations, consultez [Création de Pages de Garde](http://msdn.microsoft.com/library/windows/desktop/aa366549).  
  
 Lorsque le code fait pointer le pointeur de pile vers une adresse de cette page, une exception se produit et le système procède aux trois actions suivantes :  
  
-   Supprime la protection de PAGE\_GUARD sur la page de garde afin que le thread puisse lire et écrire des données dans la mémoire.  
  
-   Alloue une page de garde qui se trouve une page au\-dessous de la dernière.  
  
-   Rejoue l'instruction qui a déclenché l'exception.  
  
 Ainsi, le système peut augmenter la taille de la pile du thread automatiquement.  Chaque thread d'un processus a une taille de pile maximale.  La taille de la pile est définie au moment de la compilation par [\/STACK, allocations de la pile](../../build/reference/stack-stack-allocations.md), ou par l'instruction [STACKSIZE](../../build/reference/stacksize.md) dans le fichier .def pour le projet.  
  
 Lorsque cette taille de la pile maximale est dépassée, le système utilise les trois actions suivantes :  
  
-   Supprime la protection de PAGE\_GUARD sur la page de garde, comme décrit précédemment.  
  
-   Essaie d'allouer une page de garde sous de dernière.  Toutefois, cela échoue car la taille de pile maximale a été dépassée.  
  
-   Lève une exception afin que le thread puisse la gérer dans le bloc d'exception.  
  
 Notez que, à ce stade, la pile n'a plus de page de garde.  La prochaine fois que le programme élève la pile complètement à la fin, où il doit y avoir une page de garde, le programme écrit au delà de la fin de la pile et entraîne une violation d'accès.  
  
 Appelez `_resetstkoflw` pour rétablir la page de garde chaque fois que la récupération est effectuée après une exception de dépassement de capacité de la pile.  Cette fonction peut être appelée à l'intérieur du corps principal d'un bloc `__except` ou de l'extérieur d'un bloc **\_\_except** .  Toutefois, il existe quelques restrictions à quand elle doit être utilisée.  `_resetstkoflw` ne doit jamais être appelée depuis:  
  
-   Une expression de filtre.  
  
-   Une fonction filtre.  
  
-   Une fonction appelée d'une fonction de filtre.  
  
-   D'un bloc **catch**.  
  
-   D'un bloc `__finally`.  
  
 Dans ces cas, la pile n'est pas toujours suffisamment déroulée.  
  
 Les exceptions de dépassement de capacité de la pile sont générées comme les exceptions structurées, pas comme les exceptions C\+\+, donc `_resetstkoflw` n'est pas utile dans un bloc ordinaire **Catch** car il n'intercepte pas d'exception de dépassement de capacité de la pile.  Toutefois, si [\_set\_se\_translator](../../c-runtime-library/reference/set-se-translator.md) est utilisé pour implémenter un traducteur structuré des exceptions qui lève des exceptions C\+\+ \(comme dans le deuxième exemple\), une exception de dépassement de capacité de la pile provoque l'exception C\+\+ qui peut être gérée par le bloc catch C\+\+.  
  
 Il est déconseillé d'appeler **\_resetstkoflw** dans le bloc catch C\+\+ qui est atteint d'une exception levée par la fonction de transcodage structurée des exceptions.  Dans ce cas, l'espace de pile n'est pas récupéré et le pointeur de pile n'est pas réinitialisé différée tant en dehors du bloc catch, bien que les destructeurs ont été appelés pour tous les objets destructibles avant le bloc catch.  Cette fonction ne doit pas être appelée jusqu'à ce que l'espace de pile est libéré et le pointeur de pile a été réinitialisé.  Par conséquent, elle doit être appelée uniquement après avoir quitté le bloc catch.  Comme aussi peu d'espace de pile que possible doit être utilisé dans le bloc catch car un dépassement de capacité de la pile qui se produit dans le bloc catch qui lui\-même tente de récupérer d'un dépassement de capacité de la pile précédent n'est pas récupérable et peut empêcher le programme de répondre lorsque le dépassement de capacité dans le bloc catch lève une exception qui elle\-même est géré par le même bloc catch.  
  
 Il existe des situations où **\_resetstkoflw** peut échouer même si utilisé dans un emplacement approprié, par exemple dans un bloc **\_\_except** .  Si, même après avoir déroulé la pile, il ne reste pas assez d'espace de pile pour exécuter **\_resetstkoflw** sans écrire dans la dernière page de pile, **\_resetstkoflw** ne réinitialise pas la dernière page de pile comme page de garde et retourne 0, indiquant un échec.  Par conséquent, l'utilisation sécurisée de cette fonction doit inclure la vérification de la valeur de retour au lieu de supposer qu'il est possible d'utiliser la pile.  
  
 La gestion structurée des exceptions n'intercepte pas d'exception `STATUS_STACK_OVERFLOW` lorsque l'application est compilée avec `/clr` ou `/clr:pure` \(consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md)\).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_resetstkoflw`|\<malloc.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
 **Bibliothèques :** toutes les versions [Fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 L'exemple de code suivant montre une utilisation recommandée de la fonction `_resetstkoflw`.  
  
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
  
## Résultat de l'exemple  
 Sans argument de programme :  
  
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
  
### Description  
 L'exemple suivant illustre l'utilisation recommandée pour `_resetstkoflw` dans un programme où les exceptions structurées sont converties en exceptions C\+\+.  
  
### Code  
  
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
  
## Résultat de l'exemple  
  
```  
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24  
Stack overflow!  
Recovered from stack overflow and allocated 100,000 bytes using _alloca.  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [\_alloca](../../c-runtime-library/reference/alloca.md)