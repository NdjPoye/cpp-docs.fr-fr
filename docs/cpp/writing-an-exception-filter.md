---
title: "&#201;criture d&#39;un filtre d&#39;exception | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion des exceptions, filtres"
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;criture d&#39;un filtre d&#39;exception
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez gérer une exception en accédant au niveau du gestionnaire d'exceptions ou en reprenant l'exécution.  Au lieu d'utiliser le code du gestionnaire d'exceptions pour gérer l'exception et passer l'instruction, vous pouvez utiliser le *filtre* pour éliminer le problème, puis, en retournant \-1, reprendre le flux normal sans nettoyer la pile.  
  
> [!NOTE]
>  Certaines exceptions ne peuvent pas être continuées.  Si le *filtre* a la valeur –1 pour cette exception, le système lève une nouvelle exception.  Lorsque vous appelez [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552), vous déterminez si l'exception va continuer.  
  
 Par exemple, le code suivant utilise un appel de fonction dans *l'expression de filtre* : cette fonction élimine le problème puis retourne \-1 pour reprendre le flux de contrôle normal :  
  
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
  
 Il est conseillé d'utiliser un appel de fonction dans *l'expression de filtre* lorsque le *filtre* doit effectuer des opérations complexes.  L'évaluation de l'expression provoque l'exécution de la fonction, dans ce cas, `Eval_Exception`.  
  
 Notez l'utilisation de [GetExceptionCode](http://msdn.microsoft.com/library/windows/desktop/ms679356) pour déterminer l'exception.  Vous devez appeler cette fonction à l'intérieur du filtre lui\-même.  `Eval_Exception` ne peut pas appeler **GetExceptionCode**, mais le code d'exception doit lui être passé.  
  
 Ce gestionnaire passe le contrôle à un autre gestionnaire sauf si l'exception est un dépassement d'entier ou de virgule flottante.  Si tel est le cas, le gestionnaire appelle une fonction \(`ResetVars` n'est qu'un exemple, pas une fonction API\) pour réinitialiser des variables globales.  Le *Statement\-block\-2*qui est vide dans cet exemple, ne peut jamais être exécuté car `Eval_Exception` ne retourne jamais EXCEPTION\_EXECUTE\_HANDLER \(1\).  
  
 Utilisation d'un appel de fonction est une bonne technique à usage général pour traiter des expressions de filtre complexes.  Il y a deux autres fonctionnalités de langage C utiles :  
  
-   l'opérateur conditionnel ;  
  
-   l'opérateur virgule ;  
  
 L'opérateur conditionnel est souvent utile car il peut être utilisé pour rechercher un code de retour spécifique puis retourner l'une des deux valeurs différentes.  Par exemple, le filtre identifie dans le code suivant l'exception uniquement si l'exception est `STATUS_INTEGER_OVERFLOW` :  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {  
```  
  
 Dans ce cas, l'objectif de l'opérateur conditionnel consiste principalement à assurer la clarté, car le code suivant produit les mêmes résultats :  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {  
```  
  
 L'opérateur conditionnel est plus utile dans les situations où vous pouvez vouloir que le filtre ait la valeur – 1, EXCEPTION\_CONTINUE\_EXECUTION.  
  
 L'opérateur virgule vous permet d'effectuer plusieurs opérations indépendantes dans une expression unique.  Cela a pour effet approximatif d'exécuter plusieurs instructions puis de retourner la valeur de la dernière expression.  Par exemple, le code suivant enregistre le code d'exception dans une variable puis le teste :  
  
```  
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )  
```  
  
## Voir aussi  
 [Écriture d'un gestionnaire d'exceptions](../cpp/writing-an-exception-handler.md)   
 [Gestion structurée des exceptions](../cpp/structured-exception-handling-c-cpp.md)