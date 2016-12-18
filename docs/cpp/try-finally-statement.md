---
title: "try-finally, instruction | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__try"
  - "__leave_cpp"
  - "__leave"
  - "__finally_cpp"
  - "__try_cpp"
  - "__finally"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__finally (mot clé) (C++)"
  - "__finally (mot clé) (C++), syntaxe de l'instruction try-finally"
  - "__leave (mot clé) (C++)"
  - "__leave (mot clé) (C++), try-finally (instruction)"
  - "__try (mot clé) (C++)"
  - "gestion structurée des exceptions, try-finally"
  - "try-catch (mot clé) (C++), try-finally (mot clé)"
  - "try-finally (mot clé) (C++)"
ms.assetid: 826e0347-ddfe-4f6e-a7bc-0398e0edc7c2
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# try-finally, instruction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 La syntaxe suivante décrit l'instruction `try-finally` :  
  
```  
__try {  
   // guarded code  
}  
__finally {  
   // termination code  
}  
```  
  
## Grammaire  
 *try\-finally\-statement* :  
 `__try` *compound\-statement*  
  
 `__finally` *compound\-statement*  
  
 L'instruction `try-finally` est une extension Microsoft des langages C et C\+\+ qui permet aux applications cibles de garantir l'exécution du code de nettoyage lorsque l'exécution d'un bloc de code est interrompue.  Le nettoyage se compose de tâches telles que la désallocation de mémoire, la fermeture de fichiers et la libération des handles de fichiers.  L'instruction `try-finally` est particulièrement utile pour les routines qui ont plusieurs endroits où un contrôle est effectué pour une erreur qui peut provoquer un retour prématuré de la routine.  
  
 Pour plus d'informations et pour obtenir un exemple de code, consultez [Instruction try\-except](../cpp/try-except-statement.md).  Pour plus d'informations sur la gestion structurée des exceptions en général, consultez [Gestion structurée des exceptions](../cpp/structured-exception-handling-c-cpp.md).  Pour plus d'informations sur la gestion des exceptions dans les applications managées, consultez [Gestion des exceptions sous \/clr](../windows/exception-handling-cpp-component-extensions.md).  
  
> [!NOTE]
>  La gestion structurée des exceptions fonctionne avec Win32 pour les fichiers sources C et C\+\+.  Toutefois, elle n'est pas conçue spécifiquement pour C\+\+.  Vous pouvez vous assurer que votre code est plus portable en utilisant la gestion des exceptions C\+\+.  En outre, la gestion des exceptions C\+\+ est plus souple, car elle permet de traiter des exceptions de tout type.  Pour les programmes C\+\+, il est recommandé d'utiliser le mécanisme de gestion des exceptions C\+\+ \(instructions [try, catch et throw](../cpp/try-throw-and-catch-statements-cpp.md)\).  
  
 L'instruction composée après la clause `__try` est la section protégée.  L'instruction composée après la clause `__finally` est le gestionnaire de terminaisons.  Le gestionnaire spécifie un jeu d'actions qui s'exécutent lorsque la section protégée est fermée, que la section protégée soit fermée par une exception \(fin anormale\) ou par un passage standard \(fin normale\).  
  
 Le contrôle atteint une instruction `__try` par exécution séquentielle simple \(passage\).  Lorsque le contrôle pénètre dans `__try`, son gestionnaire associé devient actif.  Si le flux de contrôle atteint la fin du bloc try, l'exécution se produit de la façon suivante :  
  
1.  Le gestionnaire de terminaisons est appelé.  
  
2.  Lorsque le gestionnaire de terminaisons se termine, l'exécution reprend après l'instruction `__finally`.  Quelle que soit la façon dont la section protégée se termine \(par exemple, via `goto` hors du corps protégé ou via une instruction `return`\), le gestionnaire de terminaisons est exécuté avant \(`before`\) que le flux de contrôle ne sorte de la section protégée.  
  
     Une instruction **\_\_finally** ne bloque pas la recherche d'un gestionnaire d'exceptions approprié.  
  
 Si une exception se produit dans le bloc `__try`, le système d'exploitation doit rechercher un gestionnaire pour l'exception, sinon le programme échoue.  Si un gestionnaire est trouvé, tous les blocs `__finally` sont exécutés et l'exécution reprend dans le gestionnaire.  
  
 Par exemple, supposons qu'une série d'appels de fonction lie la fonction A à la fonction D, comme indiqué dans l'illustration suivante.  Chaque fonction a un gestionnaire de terminaisons.  Si une exception est levée dans la fonction D et gérée dans A, les gestionnaires de terminaisons sont appelés dans l'ordre suivant à mesure que le système déroule la pile : D, C, B.  
  
 ![Fin d'un ordre d'exécution de gestionnaire](../cpp/media/vc38cx1.png "vc38CX1")  
Fin de l'ordre d'exécution du gestionnaire  
  
> [!NOTE]
>  Le comportement de try\-finally est différent d'autres langages qui prennent en charge l'utilisation de **finally**, tel que C\#.  Un `__try` unique peut avoir l'un ou l'autre, `__finally` et `__except`, mais pas les deux.  Si les deux doivent être utilisés conjointement, une instruction try\-except externe doit entourer l'instruction try\-finally interne.  Les règles qui spécifient le moment d'exécution de chaque blocs sont également différentes.  
  
## Mot clé \_\_leave  
 Le mot clé `__leave` est valide uniquement dans la section protégée d'une instruction `try-finally` et il permet de sauter à la fin de la section protégée.  L'exécution continue à la première instruction dans le gestionnaire de terminaisons.  
  
 Une instruction `goto` peut également sortir de la section protégée, mais elle dégrade les performances, car elle appelle le déroulement de la pile.  L'instruction `__leave` est plus efficace, car elle n'entraîne pas le déroulement de la pile.  
  
## Arrêt anormal  
 Le fait de quitter une instruction `try-finally` à l'aide de la fonction runtime [longjmp](../c-runtime-library/reference/longjmp.md) est considéré comme un arrêt anormal.  Il est non conforme de sauter dans une instruction `__try`, mais conforme d'en sortir d'une.  Toutes les instructions `__finally` actives entre le point de départ \(arrêt normal du bloc `__try`\) et la destination \(le bloc `__except` qui gère l'exception\) doivent être exécutées.  Cela s'appelle un déroulement local.  
  
 Si un bloc **try** est prématurément arrêté, pour une raison quelconque, notamment une sortie du bloc, le système exécute le bloc **finally** associé dans le cadre du processus de déroulement de la pile.  Dans ce cas, la fonction [AbnormalTermination](http://msdn.microsoft.com/library/windows/desktop/ms679265) retourne TRUE si elle est appelée à partir du bloc **finally** ; sinon, elle retourne FALSE.  
  
 Le gestionnaire de terminaisons n'est pas appelé si un processus est arrêté au milieu de l'exécution d'une instruction `try-finally`.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Écriture d'un gestionnaire des terminaisons](../cpp/writing-a-termination-handler.md)   
 [Gestion structurée des exceptions](../cpp/structured-exception-handling-c-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Termination\-Handler Syntax](http://msdn.microsoft.com/library/windows/desktop/ms681393)