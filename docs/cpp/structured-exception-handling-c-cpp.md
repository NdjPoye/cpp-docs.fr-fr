---
title: "Gestion structur&#233;e des exceptions (C/C++) | Microsoft Docs"
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
  - "gestion d'exceptions C++, gestionnaires d'exceptions"
  - "gestion d'exceptions C++, gestionnaires de terminaisons"
  - "gestion structurée des exceptions"
  - "gestionnaires de terminaisons, gérer les exceptions en C++"
  - "try-catch (mot clé) (C++), gestionnaires d'exceptions"
  - "try-catch (mot clé) (C++), gestionnaires de terminaisons"
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion structur&#233;e des exceptions (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bien que Windows et Visual C\+\+ prennent en charge la gestion structurée des exceptions \(SEH\), nous vous recommandons d'utiliser la gestion des exceptions C\+\+ conforme à la norme ISO, car elle rend le code plus portable et plus flexible.  Néanmoins, vous devrez peut\-être encore utiliser SEH dans le code existant ou pour des types particuliers de programmes.  
  
## Section spécifique à Microsoft  
  
## Grammaire  
 *try\-except\-statement* :  
  
 `__try` *compound\-statement*  
  
 `__except` \( `expression` \) *compound\-statement*  
  
## Notes  
 Avec SEH, vous pouvez garantir que les ressources telles que les blocs de mémoire et les fichiers seront corrects si l'exécution se termine de façon inattendue.  Vous pouvez également gérer des problèmes spécifiques \(par exemple, une mémoire insuffisante\) en utilisant un code structuré concis qui ne repose pas sur les instructions `goto` ni sur des tests élaborés de codes de retour.  
  
 Les instructions try\-except et try\-finally référencées dans cet article sont des extensions Microsoft du langage C.  Elles prennent en charge SEH en permettant aux applications de prendre le contrôle d'un programme après des événements qui termineraient sinon son exécution.  Bien que la gestion SEH fonctionne avec des fichiers sources C\+\+, elle n'est pas spécifiquement conçue pour C\+\+.  Si vous l'utilisez dans un programme C\+\+ que vous compilez en utilisant l'option [\/EH](../build/reference/eh-exception-handling-model.md) avec certains modificateurs, des destructeurs d'objets locaux sont appelés, mais d'autres comportements d'exécution non prévus peuvent apparaître.  \(Pour obtenir une illustration, consultez l'exemple présenté plus loin dans cet article.\)  Dans la plupart des cas, au lieu de SEH, nous vous recommandons d'utiliser la [gestion des exceptions C\+\+](../cpp/try-throw-and-catch-statements-cpp.md) conforme à la norme ISO, que Visual C\+\+ prend également en charge.  En utilisant la gestion des exceptions C\+\+, vous pouvez garantir que votre code est plus portable et gérer les exceptions de tout type.  
  
 Si vous avez des modules C qui utilisent SEH, vous pouvez les mélanger avec des modules C\+\+ qui utilisent la gestion des exceptions C\+\+.  Pour plus d'informations, consultez [Différences de gestion des exceptions](../cpp/exception-handling-differences.md).  
  
 Il existe deux mécanismes de gestion SEH :  
  
-   Des [gestionnaires d'exceptions](../cpp/writing-an-exception-handler.md), qui peuvent répondre à l'exception ou la faire disparaître.  
  
-   Des [gestionnaires de terminaisons](../cpp/writing-a-termination-handler.md), qui sont appelés quand une exception provoque l'arrêt d'un bloc de code.  
  
 Ces deux types de gestionnaires sont distincts, mais sont étroitement liés via un processus appelé « déroulement de la pile ». Quand une exception se produit, Windows cherche le gestionnaire d'exceptions le plus récemment installé qui est actif.  Le gestionnaire peut effectuer l'une des trois opérations suivantes :  
  
-   Il ne reconnaît pas l'exception et passe le contrôle à d'autres gestionnaires.  
  
-   Il reconnaît l'exception, mais la fait disparaître.  
  
-   Il reconnaît l'exception et la gère.  
  
 Le gestionnaire d'exceptions qui reconnaît l'exception peut ne pas être dans la fonction qui s'exécutait quand l'exception s'est produite.  Dans certains cas, il peut s'agir d'une fonction beaucoup plus élevée dans la pile.  La fonction en cours d'exécution et toutes les autres fonctions sur le frame de pile sont terminées.  Pendant ce processus, la pile est « déroulée »; autrement dit, les variables locales des fonctions terminées, sauf si elles ont la valeur `static`, sont effacées de la pile.  
  
 Tout en déroulant la pile, le système d'exploitation appelle tous les gestionnaires de terminaisons que vous avez écrits pour chaque fonction.  En utilisant un gestionnaire de terminaisons, vous pouvez nettoyer les ressources qui autrement resteraient ouvertes en raison d'un achèvement anormal.  Si vous êtes entré dans une section critique, vous pouvez la quitter via le gestionnaire de terminaisons.  Si le programme doit s'arrêter, vous pouvez effectuer d'autres tâches de gestion interne telles que la fermeture et la suppression des fichiers temporaires.  
  
 Pour plus d'informations, voir :  
  
-   [Écriture d'un gestionnaire d'exceptions](../cpp/writing-an-exception-handler.md)  
  
-   [Écriture d'un gestionnaire des terminaisons](../cpp/writing-a-termination-handler.md)  
  
-   [Utilisation de la gestion structurée des exceptions avec C\+\+](../cpp/using-structured-exception-handling-with-cpp.md)  
  
## Exemple  
 Comme indiqué précédemment, les destructeurs d'objets locaux sont appelés si vous utilisez SEH dans un programme C\+\+ et le compilez en utilisant l'option **\/EH** avec certains modificateurs, par exemple, **\/EHsc** et **\/EHa**.  Toutefois, le comportement pendant l'exécution peut ne pas être celui prévu si vous utilisez également des exceptions C\+\+.  L'exemple suivant illustre ces différences de comportement.  
  
```cpp  
#include <stdio.h>  
#include <Windows.h>  
#include <exception>  
  
class TestClass  
{  
public:  
    ~TestClass()  
    {  
        printf("Destroying TestClass!\r\n");  
    }  
};  
  
__declspec(noinline) void TestCPPEX()  
{  
#ifdef CPPEX  
    printf("Throwing C++ exception\r\n");  
    throw std::exception("");  
#else  
    printf("Triggering SEH exception\r\n");  
    volatile int *pInt = 0x00000000;  
    *pInt = 20;  
#endif  
}  
  
__declspec(noinline) void TestExceptions()  
{  
    TestClass d;  
    TestCPPEX();  
}  
  
int main()  
{  
    __try  
    {  
        TestExceptions();  
    }  
    __except(EXCEPTION_EXECUTE_HANDLER)  
    {  
        printf("Executing SEH __except block\r\n");  
    }  
  
    return 0;  
}  
  
```  
  
 Si vous utilisez **\/EHsc** pour compiler ce code, mais que le contrôle `CPPEX` de test local n'est pas défini, il n'y a pas d'exécution du destructeur de `TestClass` et la sortie ressemble à ceci :  
  
  **Déclenchement d'une exception SEH**  
**Exécution du bloc SEH \_\_except** Si vous utilisez **\/EHsc** pour compiler le code et que `CPPEX` est défini à l'aide de `/DCPPEX` \(afin qu'une exception C\+\+ soit levée\), le destructeur de `TestClass` s'exécute et la sortie ressemble à ceci :  
  
  **Levée d'une exception C\+\+**  
**Destruction de TestClass \!  Exécution du bloc SEH \_\_except**  Si vous utilisez **\/EHa** pour compiler le code, le destructeur de `TestClass` s'exécute indépendamment de la levée de l'exception en utilisant `std::throw` ou SEH \(`CPPEX` défini ou non\).  La sortie ressemble à ceci :  
  
  **Levée d'une exception C\+\+**  
**Destruction de TestClass \!  Exécution du bloc SEH \_\_except**  Pour plus d'informations, consultez [\/EH \(Modèle de gestion des exceptions\)](../build/reference/eh-exception-handling-model.md).  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Gestion des exceptions](../cpp/exception-handling-in-visual-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [\<exception\>](../standard-library/exception.md)   
 [Gestion des erreurs et des exceptions](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [Gestion structurée des exceptions \(Windows\)](http://msdn.microsoft.com/library/windows/desktop/ms680657.aspx)