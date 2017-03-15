---
title: "try-except, instruction | Microsoft Docs"
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
  - "_abnormal_termination_cpp"
  - "_exception_code_cpp"
  - "EXCEPTION_CONTINUE_SEARCH"
  - "_exception_info"
  - "__except"
  - "EXCEPTION_CONTINUE_EXECUTION"
  - "_exception_code"
  - "__except_cpp"
  - "_exception_info_cpp"
  - "EXCEPTION_EXECUTE_HANDLER"
  - "_abnormal_termination"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__try (mot clé) (C++)"
  - "_abnormal_termination (mot clé) (C++)"
  - "_exception_code (mot clé) (C++)"
  - "_exception_info (mot clé) (C++)"
  - "EXCEPTION_CONTINUE_EXECUTION (macro)"
  - "EXCEPTION_CONTINUE_SEARCH (macro)"
  - "EXCEPTION_EXECUTE_HANDLER (macro)"
  - "GetExceptionCode (fonction)"
  - "try-catch (mot clé) (C++), try-except (mot clé) (C++)"
  - "try-except (mot clé) (C++)"
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# try-except, instruction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 La syntaxe suivante décrit une instruction try\-except :  
  
## Syntaxe  
  
```  
  
      __try   
{  
   // guarded code  
}  
__except ( expression )  
{  
   // exception handler code  
}  
```  
  
## Notes  
 L'instruction **try\-except** est une extension Microsoft des langages C et C\+\+ qui permet aux applications cibles de prendre le contrôle lorsque des événements surviennent qui terminent normalement l'exécution du programme.  Ces événements sont appelés « exceptions » et le mécanisme de gestion des exceptions s'appelle « gestion structurée des exceptions ».  
  
 Pour obtenir des informations connexes, consultez l'article [Instruction try\-finally](../cpp/try-finally-statement.md).  
  
 Les exceptions peuvent être basées sur le matériel ou sur des logiciels.  Même quand les applications ne peuvent pas complètement récupérer à partir d'exceptions matérielles ou logicielles, la gestion structurée des exceptions permet d'afficher des informations sur l'erreur et d'intercepter l'état interne de l'application pour favoriser le diagnostic du problème.  Ceci s'avère particulièrement utile pour les problèmes intermittents qui ne peuvent pas être facilement reproduits.  
  
> [!NOTE]
>  La gestion structurée des exceptions fonctionne avec Win32 pour les fichiers sources C et C\+\+.  Toutefois, elle n'est pas conçue spécifiquement pour C\+\+.  Vous pouvez vous assurer que votre code est plus portable en utilisant la gestion des exceptions C\+\+.  En outre, la gestion des exceptions C\+\+ est plus souple, car elle permet de traiter des exceptions de tout type.  Pour les programmes C\+\+, il est recommandé d'utiliser le mécanisme de gestion des exceptions C\+\+ \(instructions [try, catch et throw](../cpp/try-throw-and-catch-statements-cpp.md)\).  
  
 L'instruction composée après la clause `__try` constitue le corps ou la section protégée.  L'instruction composée après la clause `__except` constitue le gestionnaire d'exceptions.  Le gestionnaire spécifie un ensemble d'actions à entreprendre si une exception est levée pendant l'exécution du corps de la section protégée.  L'exécution se déroule comme suit :  
  
1.  La section protégée est exécutée.  
  
2.  Si aucune exception ne se produit pendant l'exécution de la section protégée, l'exécution se poursuit à l'instruction située après la clause `__except`.  
  
3.  Si une exception se produit pendant l'exécution de la section protégée ou dans une routine quelconque appelée par la section protégée, l'*expression* `__except` \(appelée expression de *filtre*\) est évaluée et sa valeur détermine comment l'exception est gérée.  Il existe trois valeurs :  
  
     **EXCEPTION\_CONTINUE\_EXECUTION \(–1\)** L'exception est fermée.  Poursuivre l'exécution au point où l'exception s'est produite.  
  
     **EXCEPTION\_CONTINUE\_SEARCH \(0\)** L'exception n'est pas reconnue.  Poursuivre la recherche d'un gestionnaire dans la pile, en premier pour qu'il contienne des instructions **try\-except**, puis pour les gestionnaires avec la priorité la plus élevée suivante.  
  
     **EXCEPTION\_EXECUTE\_HANDLER \(1\)** L'exception est reconnue.  Transférer le contrôle au gestionnaire d'exceptions en exécutant l'instruction composée `__except`, puis poursuivre l'exécution après le bloc `__except`.  
  
 Comme l'expression \_\_**except** est évaluée comme une expression C, elle est limitée à une valeur unique, à l'opérateur d'expression conditionnelle ou à l'opérateur virgule.  Si un traitement plus étendu est requis, l'expression peut appeler une routine qui retourne l'une des trois valeurs répertoriées ci\-dessus.  
  
 Chaque application peut avoir son propre gestionnaire d'exceptions.  
  
 Il n'est pas valide de sauter dans une instruction `__try`, mais il est valide de sauter hors d'une telle instruction.  Le gestionnaire d'exceptions n'est pas appelé si un processus est terminé au milieu de l'exécution d'une instruction **try\-except**.  
  
 Pour plus d'informations, consultez l'article de la Base de connaissances Q315937 : PROCÉDURE : interception du dépassement de capacité de la pile dans une application Visual C\+\+.  
  
## Mot clé \_\_leave  
 Le mot clé `__leave` est valide uniquement dans la section protégée d'une instruction `try-except` et il permet de sauter à la fin de la section protégée.  L'exécution se poursuit à la première instruction située après le gestionnaire d'exceptions.  
  
 Une instruction `goto` permet également de sortir de la section protégée sans altérer les performances, contrairement à une instruction `try-finally`, car aucun déroulement de pile ne se produit.  Toutefois, nous vous recommandons d'utiliser le mot clé `__leave` plutôt qu'une instruction `goto`, car vous êtes moins enclin à commettre une erreur de programmation si la section protégée est grande ou complexe.  
  
### Fonctions intrinsèques de gestion structurée des exceptions  
 La gestion structurée des exceptions fournit deux fonctions intrinsèques pouvant être utilisées avec l'instruction **try\-except** : **GetExceptionCode** et **GetExceptionInformation**.  
  
 **GetExceptionCode** retourne le code \(entier 32 bits\) de l'exception.  
  
 La fonction intrinsèque **GetExceptionInformation** retourne un pointeur vers une structure contenant des informations supplémentaires sur l'exception.  Ce pointeur vous permet d'accéder à l'état de l'ordinateur qui existait au moment d'une exception matérielle.  La structure est la suivante :  
  
```  
struct _EXCEPTION_POINTERS {  
      EXCEPTION_RECORD *ExceptionRecord,  
      CONTEXT *ContextRecord }  
```  
  
 Les types pointeur \_**EXCEPTION\_RECORD** et \_**CONTEXT** sont définis dans le fichier Include EXCPT.H.  
  
 Vous pouvez utiliser **GetExceptionCode** dans le gestionnaire d'exceptions.  Toutefois, vous pouvez utiliser **GetExceptionInformation** uniquement dans l'expression de filtre d'exception.  Les informations qu'il désigne sont généralement sur la pile et ne sont plus disponibles lorsque le contrôle est transféré au gestionnaire d'exceptions.  
  
 La fonction intrinsèque **AbnormalTermination** est disponible dans un gestionnaire de terminaisons.  Elle retourne 0 si le corps de l'instruction `try-finally` se termine séquentiellement.  Dans tous les autres cas, elle retourne 1.  
  
 EXCPT.H définit d'autres noms pour les fonctions intrinsèques suivantes :  
  
 **GetExceptionCode** est équivalent à \_exception\_code  
  
 **GetExceptionInformation** est équivalent à \_exception\_info  
  
 **AbnormalTermination** est équivalent à \_abnormal\_termination  
  
## Exemple  
 `// exceptions_try_except_Statement.cpp`  
  
 `// Example of try-except and try-finally statements`  
  
 `#include <stdio.h>`  
  
 `#include <windows.h> // for EXCEPTION_ACCESS_VIOLATION`  
  
 `#include <excpt.h>`  
  
 `int filter(unsigned int code, struct _EXCEPTION_POINTERS *ep) {`  
  
 `puts("in filter.");`  
  
 `if (code == EXCEPTION_ACCESS_VIOLATION) {`  
  
 `puts("caught AV as expected.");`  
  
 `return EXCEPTION_EXECUTE_HANDLER;`  
  
 `}`  
  
 `else {`  
  
 `puts("didn't catch AV, unexpected.");`  
  
 `return EXCEPTION_CONTINUE_SEARCH;`  
  
 `};`  
  
 `}`  
  
 `int main()`  
  
 `{`  
  
 `int* p = 0x00000000;   // pointer to NULL`  
  
 `puts("hello");`  
  
 `__try{`  
  
 `puts("in try");`  
  
 `__try{`  
  
 `puts("in try");`  
  
 `*p = 13;    // causes an access violation exception;`  
  
 `}__finally{`  
  
 `puts("in finally. termination: ");`  
  
 `puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");`  
  
 `}`  
  
 `}__except(filter(GetExceptionCode(), GetExceptionInformation())){`  
  
 `puts("in except");`  
  
 `}`  
  
 `puts("world");`  
  
 `}`  
  
## Sortie  
  
```  
hello  
in try  
in try  
in filter.  
caught AV as expected.  
in finally. termination:  
        abnormal  
in except  
world  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Écriture d'un gestionnaire d'exceptions](../cpp/writing-an-exception-handler.md)   
 [Gestion structurée des exceptions](../cpp/structured-exception-handling-c-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)