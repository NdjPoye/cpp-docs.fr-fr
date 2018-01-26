---
title: Recommencez-EXCEPT, instruction | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- EXCEPTION_CONTINUE_SEARCH
- _exception_info
- __except
- EXCEPTION_CONTINUE_EXECUTION
- _exception_code
- __except_cpp
- _exception_info_cpp
- EXCEPTION_EXECUTE_HANDLER
- _abnormal_termination
dev_langs: C++
helpviewer_keywords:
- __try keyword [C++]
- EXCEPTION_CONTINUE_EXECUTION macro
- EXCEPTION_CONTINUE_SEARCH macro
- EXCEPTION_EXECUTE_HANDLER macro
- GetExceptionCode function
- try-catch keyword [C++], try-except keyword [C++]
- _exception_code keyword [C++]
- try-except keyword [C++]
- _exception_info keyword [C++]
- _abnormal_termination keyword [C++]
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 24be4e7fd6b4dc95d9964e69943a94ecad947a47
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="try-except-statement"></a>try-except, instruction

**Section spécifique à Microsoft**  
Le **essayez-sauf** instruction est une extension Microsoft c et langages C++ qui prend en charge structurée des exceptions.  

## <a name="syntax"></a>Syntaxe  
  
> **__try**   
> {  
>    code protégé  
> }  
> **__except** ( *expression* )  
> {  
>    code du Gestionnaire d’exception  
> }  

## <a name="remarks"></a>Notes

Le **essayez-sauf** instruction est une extension Microsoft c et langages C++ qui permet aux applications cibles obtenir un contrôlent lorsque des événements qui terminent normalement l’exécution du programme surviennent. Ces événements sont appelés *exceptions*, et le mécanisme des exceptions s’appelle *structurée des exceptions* (SEH).

Pour plus d’informations, consultez la [try-finally, instruction](../cpp/try-finally-statement.md).

Les exceptions peuvent être basées sur le matériel ou sur des logiciels. Même quand les applications ne peuvent pas complètement récupérer à partir d'exceptions matérielles ou logicielles, la gestion structurée des exceptions permet d'afficher des informations sur l'erreur et d'intercepter l'état interne de l'application pour favoriser le diagnostic du problème. Ceci s'avère particulièrement utile pour les problèmes intermittents qui ne peuvent pas être facilement reproduits.

> [!NOTE]
> La gestion structurée des exceptions fonctionne avec Win32 pour les fichiers sources C et C++. Toutefois, elle n'est pas conçue spécifiquement pour C++. Vous pouvez vous assurer que votre code est plus portable en utilisant la gestion des exceptions C++. En outre, la gestion des exceptions C++ est plus souple, car elle permet de traiter des exceptions de tout type. Pour les programmes C++, il est recommandé d’utiliser le mécanisme de gestion des exceptions C++ ([try, catch et throw](../cpp/try-throw-and-catch-statements-cpp.md) instructions).

L'instruction composée après la clause `__try` constitue le corps ou la section protégée. L'instruction composée après la clause `__except` constitue le gestionnaire d'exceptions. Le gestionnaire spécifie un ensemble d'actions à entreprendre si une exception est levée pendant l'exécution du corps de la section protégée. L'exécution se déroule comme suit :

1. La section protégée est exécutée.

2. Si aucune exception ne se produit pendant l'exécution de la section protégée, l'exécution se poursuit à l'instruction située après la clause `__except`.  

3. Si une exception se produit pendant l’exécution de la section protégée ou dans une routine de la section protégée appelle, les `__except` *expression* (appelée la *filtre* expression) est évaluée et la valeur Détermine comment l’exception est gérée. Il existe trois valeurs :

   **EXCEPTION_CONTINUE_EXECUTION (-1)** Exception est fermée. Poursuivre l'exécution au point où l'exception s'est produite.

   **EXCEPTION_CONTINUE_SEARCH (0)** Exception n’est pas reconnue. Poursuivre la recherche d’un gestionnaire dans la pile, en premier pour qu’il contienne des instructions **try-except**, puis pour les gestionnaires avec la priorité la plus élevée suivante.

   **Exception_execute_handler (1)** l’Exception est reconnue. Transférer le contrôle au gestionnaire d'exceptions en exécutant l'instruction composée `__except`, puis poursuivre l'exécution après le bloc `__except`.

L'expression `__except` étant évaluée comme une expression C, elle est limitée à une valeur unique, l'opérateur d'expression conditionnelle, ou l'opérateur virgule. Si un traitement plus étendu est requis, l'expression peut appeler une routine qui retourne l'une des trois valeurs répertoriées ci-dessus.

Chaque application peut avoir son propre gestionnaire d'exceptions.

Il n'est pas valide de sauter dans une instruction `__try`, mais il est valide de sauter hors d'une telle instruction. Le Gestionnaire d’exceptions n’est pas appelé si un processus est terminé au milieu de l’exécution une **essayez-sauf** instruction.  
  
Pour plus d'informations, consultez l'article de la Base de connaissances Q315937 : PROCÉDURE : interception du dépassement de capacité de la pile dans une application Visual C++.  
  
## <a name="the-leave-keyword"></a>Mot clé __leave

Le `__leave` mot clé est valide uniquement dans la section protégée d’un **essayez-sauf** instruction et son effet consiste à accéder à la fin de la section protégée. L'exécution se poursuit à la première instruction située après le gestionnaire d'exceptions.

A `goto` instruction peut également sortir de la section protégée, et sans altérer les performances comme il le fait un **try-finally** instruction, car le déroulement de pile n’a pas lieu. Toutefois, nous vous recommandons d'utiliser le mot clé `__leave` plutôt qu'une instruction `goto`, car vous êtes moins enclin à commettre une erreur de programmation si la section protégée est grande ou complexe.

### <a name="structured-exception-handling-intrinsic-functions"></a>Fonctions intrinsèques de gestion structurée des exceptions

Gestion structurée des exceptions fournit deux fonctions intrinsèques qui sont disponibles à utiliser avec le **essayez-sauf** instruction : `GetExceptionCode` et `GetExceptionInformation`.

`GetExceptionCode`Retourne le code (un entier 32 bits) de l’exception.

La fonction intrinsèque `GetExceptionInformation` retourne un pointeur vers une structure contenant des informations supplémentaires sur l’exception. Ce pointeur vous permet d'accéder à l'état de l'ordinateur qui existait au moment d'une exception matérielle. La structure est la suivante :

```cpp  
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS; 
```  

Les types pointeur `PEXCEPTION_RECORD` et `PCONTEXT` sont définis dans le fichier include \<winnt.h >, et `_EXCEPTION_RECORD` et `_CONTEXT` sont définis dans le fichier include \<excpt.h >

Vous pouvez utiliser `GetExceptionCode` dans le Gestionnaire d’exceptions. Toutefois, vous pouvez utiliser `GetExceptionInformation` uniquement dans l’expression de filtre d’exception. Les informations qu'il désigne sont généralement sur la pile et ne sont plus disponibles lorsque le contrôle est transféré au gestionnaire d'exceptions.

La fonction intrinsèque `AbnormalTermination` est disponible dans un gestionnaire de terminaisons. Retourne 0 si le corps de la **try-finally** instruction se termine séquentiellement. Dans tous les autres cas, elle retourne 1.

excpt.h définit d’autres noms pour ces fonctions intrinsèques :

`GetExceptionCode`est équivalent à`_exception_code`

 `GetExceptionInformation`est équivalent à`_exception_info`

 `AbnormalTermination`est équivalent à`_abnormal_termination`
  
## <a name="example"></a>Exemple

```cpp
// exceptions_try_except_Statement.cpp
// Example of try-except and try-finally statements
#include <stdio.h>
#include <windows.h> // for EXCEPTION_ACCESS_VIOLATION
#include <excpt.h>

int filter(unsigned int code, struct _EXCEPTION_POINTERS *ep)
{
    puts("in filter.");
    if (code == EXCEPTION_ACCESS_VIOLATION)
    {
        puts("caught AV as expected.");
        return EXCEPTION_EXECUTE_HANDLER;
    }
    else
    {
        puts("didn't catch AV, unexpected.");
        return EXCEPTION_CONTINUE_SEARCH;
    };
}

int main()
{
    int* p = 0x00000000;   // pointer to NULL
    puts("hello");
    __try
    {
        puts("in try");
        __try
        {
            puts("in try");
            *p = 13;    // causes an access violation exception;
        }
        __finally
        {
            puts("in finally. termination: ");
            puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");
        }
    }
    __except(filter(GetExceptionCode(), GetExceptionInformation()))
    {
        puts("in except");
    }
    puts("world");
}
```
  
## <a name="output"></a>Sortie  
  
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

## <a name="see-also"></a>Voir aussi

[L’écriture d’un gestionnaire d’exceptions](../cpp/writing-an-exception-handler.md)   
[Exceptions structurées (C/C++)](../cpp/structured-exception-handling-c-cpp.md)   
[Mots clés](../cpp/keywords-cpp.md)
