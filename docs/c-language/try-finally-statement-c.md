---
title: "try-finally, instruction&#160;(C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "try_cpp"
  - "try"
  - "finally"
  - "finally_cpp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__finally (mot clé) (C)"
  - "__finally (mot clé) (C), syntaxe de l'instruction try-finally"
  - "gestion structurée des exceptions, try-finally"
  - "try-catch (mot clé) (C)"
  - "try-catch (mot clé) (C), try-finally (mot clé) (C)"
  - "try-finally (mot clé) (C)"
ms.assetid: 514400c1-c322-4bf3-9e48-3047240b8a82
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# try-finally, instruction&#160;(C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 L'instruction `try-finally` est une extension Microsoft du langage C qui permet aux applications de garantir l'exécution du code de nettoyage lorsque l'exécution d'un bloc de code est interrompue.  Le nettoyage se compose de tâches telles que la désallocation de mémoire, la fermeture de fichiers et la libération des handles de fichiers.  L'instruction `try-finally` est particulièrement utile pour les routines qui ont plusieurs endroits où un contrôle est effectué pour une erreur qui peut provoquer un retour prématuré de la routine.  
  
 *try\-finally\-statement* :  
 **\_\_try**  *compound\-statement*  
  
 **\_\_finally**  *compound\-statement*  
  
 L'instruction composée après la clause `__try` est la section protégée.  L'instruction composée après la clause `__finally` est le gestionnaire de terminaisons.  Le gestionnaire spécifie un jeu d'actions qui s'exécutent lorsque la section protégée est fermée, que la section protégée soit fermée par une exception \(fin anormale\) ou par un passage standard \(fin normale\).  
  
 Le contrôle atteint une instruction `__try` par exécution séquentielle simple \(passage\).  Lorsque le contrôle pénètre dans l'instruction `__try`, son gestionnaire associé devient actif.  L'exécution se déroule comme suit :  
  
1.  La section protégée est exécutée.  
  
2.  Le gestionnaire de terminaisons est appelé.  
  
3.  Lorsque le gestionnaire de terminaisons se termine, l'exécution reprend après l'instruction `__finally`.  Quelle que soit la façon dont la section protégée se termine \(par exemple, via une instruction `goto` hors du corps protégé ou via une instruction `return`\), le gestionnaire de terminaisons est exécuté avant que le flux de contrôle ne sorte de la section protégée.  
  
 Le mot clé `__leave` est valide dans un bloc d'instructions `try-finally`.  L'effet exercé par `__leave` est de sauter à la fin du bloc `try-finally`.  Le gestionnaire de terminaisons est immédiatement exécuté.  Bien qu'une instruction `goto` puisse être utilisée pour obtenir le même résultat, une instruction `goto` provoque le déroulement de pile.  L'instruction `__leave` est plus efficace car elle n'implique pas le déroulement de pile.  
  
 Sortir d'une instruction `try-finally` à l'aide d'une instruction `return` ou d'une fonction runtime `longjmp` est considéré comme une fin anormale.  Il est non conforme de sauter dans une instruction `__try`, mais conforme d'en sortir d'une.  Toutes les instructions `__finally` actives entre le point de départ et la destination doivent être exécutées.  Cela s'appelle un « déroulement local ».  
  
 Le gestionnaire de terminaisons n'est pas appelé si un processus est tué tout en exécutant une instruction `try-finally`.  
  
> [!NOTE]
>  La gestion structurée des exceptions fonctionne avec les fichiers sources C et C\+\+.  Toutefois, elle n'est pas conçue spécifiquement pour C\+\+.  Vous pouvez vous assurer que votre code est plus portable en utilisant la gestion des exceptions C\+\+.  En outre, le mécanisme de gestion des exceptions C\+\+ est beaucoup plus souple, car il peut gérer les exceptions de tout type.  
  
> [!NOTE]
>  Pour les programmes C\+\+, la gestion des exceptions C\+\+ doit être utilisée à la place de la gestion structurée des exceptions.  Pour plus d'informations, consultez [Gestion des exceptions](../cpp/exception-handling-in-visual-cpp.md) dans le *Guide de référence du langage C\+\+*.  
  
 Consultez l'exemple pour l'[instruction try\-except](../c-language/try-except-statement-c.md) pour voir comment l'instruction `try-finally` fonctionne.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [try\-finally, instruction](../cpp/try-finally-statement.md)