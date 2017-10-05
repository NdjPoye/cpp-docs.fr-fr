---
title: "Écriture d’un filtre d’Exception | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exception handling, filters
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 07bce97cdac37a920716e72f88bdda2d164fc479
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="writing-an-exception-filter"></a>Écriture d'un filtre d'exception
Vous pouvez gérer une exception en accédant au niveau du gestionnaire d'exceptions ou en reprenant l'exécution. Au lieu d’utiliser le code de gestionnaire d’exceptions pour gérer l’exception et passer, vous pouvez utiliser *filtre* pour nettoyer le problème et puis, en retournant -1, reprendre le flux normal sans nettoyer la pile.  
  
> [!NOTE]
>  Certaines exceptions ne peuvent pas être continuées. Si *filtre* prend la valeur-1 pour une telle exception, le système déclenche une exception. Lorsque vous appelez [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552), vous déterminez si l’exception va continuer.  
  
 Par exemple, le code suivant utilise un appel de fonction dans le *filtre* expression : cette fonction élimine le problème et puis retourne -1 pour reprendre le flux de contrôle normal :  
  
```  
// exceptions_Writing_an_Exception_Filter.cpp  
#include <windows.h>  
int main() {  
   int Eval_Exception( int );  
  
   __try {}  
  
   __except ( Eval_Exception( GetExceptionCode( ))) {  
      ;  
   }  
  
}  
void ResetVars( int ) {}  
int Eval_Exception ( int n_except ) {  
   if ( n_except != STATUS_INTEGER_OVERFLOW &&   
      n_except != STATUS_FLOAT_OVERFLOW )   // Pass on most exceptions  
   return EXCEPTION_CONTINUE_SEARCH;  
  
   // Execute some code to clean up problem  
   ResetVars( 0 );   // initializes data to 0  
   return EXCEPTION_CONTINUE_EXECUTION;  
}  
```  
  
 Il est judicieux d’utiliser un appel de fonction dans le *filtre* expression chaque fois que *filtre* a besoin d’effectuer des opérations complexes. L'évaluation de l'expression provoque l'exécution de la fonction, dans ce cas, `Eval_Exception`.  
  
 Notez l’utilisation de [GetExceptionCode](http://msdn.microsoft.com/library/windows/desktop/ms679356) pour déterminer l’exception. Vous devez appeler cette fonction à l'intérieur du filtre lui-même. `Eval_Exception`Impossible d’appeler **GetExceptionCode**, mais il doit avoir le code d’exception lui est passé.  
  
 Ce gestionnaire passe le contrôle à un autre gestionnaire sauf si l'exception est un dépassement d'entier ou de virgule flottante. Si tel est le cas, le gestionnaire appelle une fonction (`ResetVars` n'est qu'un exemple, pas une fonction API) pour réinitialiser des variables globales. *Instruction-block-2*, dans cet exemple est vide, peut ne jamais être exécutée, car `Eval_Exception` ne retourne jamais EXCEPTION_EXECUTE_HANDLER (1).  
  
 Utilisation d'un appel de fonction est une bonne technique à usage général pour traiter des expressions de filtre complexes. Il y a deux autres fonctionnalités de langage C utiles :  
  
-   l'opérateur conditionnel ;  
  
-   l'opérateur virgule ;  
  
 L'opérateur conditionnel est souvent utile car il peut être utilisé pour rechercher un code de retour spécifique puis retourner l'une des deux valeurs différentes. Par exemple, le filtre identifie dans le code suivant l'exception uniquement si l'exception est `STATUS_INTEGER_OVERFLOW` :  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {  
```  
  
 Dans ce cas, l'objectif de l'opérateur conditionnel consiste principalement à assurer la clarté, car le code suivant produit les mêmes résultats :  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {  
```  
  
 L’opérateur conditionnel est plus utile dans les cas dans lesquels vous pourriez le filtre doit évaluer et -1, EXCEPTION_CONTINUE_EXECUTION.  
  
 L'opérateur virgule vous permet d'effectuer plusieurs opérations indépendantes dans une expression unique. Cela a pour effet approximatif d'exécuter plusieurs instructions puis de retourner la valeur de la dernière expression. Par exemple, le code suivant enregistre le code d'exception dans une variable puis le teste :  
  
```  
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )  
```  
  
## <a name="see-also"></a>Voir aussi  
 [L’écriture d’un gestionnaire d’exceptions](../cpp/writing-an-exception-handler.md)   
 [Gestion structurée des exceptions (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
