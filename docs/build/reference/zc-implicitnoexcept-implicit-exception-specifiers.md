---
title: "/Zc:implicitNoexcept (sp&#233;cificateurs d&#39;exceptions implicites) | Microsoft Docs"
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
  - "/Zc:implicitNoexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc:implicitNoexcept"
  - "Zc:implicitNoexcept"
  - "-Zc:implicitNoexcept"
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:implicitNoexcept (sp&#233;cificateurs d&#39;exceptions implicites)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Quand l'option **\/Zc:implicitNoexcept** est spécifiée, le compilateur ajoute un spécificateur d'exception [noexcept](../../cpp/noexcept-cpp.md) implicite aux fonctions membres spéciales définies par le compilateur et aux destructeurs et annulateurs d'allocation définis par l'utilisateur.  Par défaut, **\/Zc:implicitNoexcept** est activé pour être conforme à la norme ISO C\+\+11.  La désactivation de cette option désactive `noexcept` implicite sur les annulateurs d'allocation et les destructeurs définis par l'utilisateur et sur les fonctions membres spéciales définies par le compilateur.  
  
## Syntaxe  
  
```vb  
/Zc:implicitNoexcept[-]  
```  
  
#### Paramètres  
  
## Notes  
 Par défaut, et si **\/Zc:implicitNoexcept** est spécifié, le compilateur suit la section 15.4 de la norme ISO C\+\+11 et ajoute implicitement un spécificateur d'exception `noexcept` à chaque fonction membre spéciale déclarée implicitement ou explicitement utilisée par défaut \(constructeur par défaut, constructeur de copie, constructeur de déplacement, destructeur, opérateur d'assignation de copie ou opérateur d'assignation de déplacement\) et à chaque fonction destructeur ou annulateur d'allocation définie par l'utilisateur.  Un annulateur d'allocation défini par l'utilisateur possède un spécificateur d'exception `noexcept(true)` implicite.  Pour les destructeurs définis par l'utilisateur, le spécificateur d'exception implicite est `noexcept(true)` à moins qu'une classe de base ou une classe membre contenue possède un destructeur qui n'est pas `noexcept(true)`.  Pour les fonctions membres spéciales générées par le compilateur, si une fonction quelconque directement appelée par cette fonction est effectivement `noexcept(false)`, le spécificateur d'exception implicite est `noexcept(false)`.  Sinon, le spécificateur d'exception implicite est `noexcept(true)`.  
  
 Le compilateur ne génère pas un spécificateur d'exception implicite pour les fonctions déclarées à l'aide de spécificateurs `noexcept` ou `throw` explicites ou d'un attribut `__declspec(nothrow)`.  
  
 Si l'option est désactivée en spécifiant **\/Zc:implicitNoexcept\-**, aucun spécificateur d'exception implicite n'est généré par le compilateur.  Ce comportement est identique à celui de Visual Studio 2013, où les destructeurs et les annulateurs d'allocation qui n'avaient pas de spécificateur d'exception pouvaient avoir des instructions `throw`.  Par défaut, et quand **\/Zc:implicitNoexcept** est spécifié, si une instruction `throw` est rencontrée au moment de l'exécution dans une fonction dotée d'un spécificateur `noexcept(true)` implicite, elle provoque un appel immédiat de `std::terminate` et le comportement de déroulement normal pour les gestionnaires d'exceptions n'est pas garanti.  Pour aider à identifier cette situation, le compilateur génère l'[Avertissement du compilateur \(niveau 1\) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md).  Si l'instruction `throw` est intentionnelle, nous vous recommandons de changer votre déclaration de fonction pour avoir un spécificateur `noexcept(false)` explicite au lieu d'utiliser **\/Zc:implicitNoexcept\-**.  
  
 Cet exemple montre comment un destructeur défini par l'utilisateur dépourvu de spécificateur d'exception explicite se comporte quand l'option **\/Zc:implicitNoexcept** est définie ou désactivée.  Pour afficher le comportement quand l'option est définie, compilez en utilisant `cl /EHsc /W4 implicitNoexcept.cpp`.  Pour afficher le comportement quand l'option est désactivée, compilez en utilisant `cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp`.  
  
```  
// implicitNoexcept.cpp  
// Compile by using: cl /EHsc /W4 implicitNoexcept.cpp  
// Compile by using: cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp  
  
#include <iostream>  
#include <cstdlib>      // for std::exit, EXIT_FAILURE, EXIT_SUCCESS  
#include <exception>    // for std::set_terminate  
  
void my_terminate()  
{  
    std::cout << "Unexpected throw caused std::terminate" << std::endl;  
    std::cout << "Exit returning EXIT_FAILURE" << std::endl;  
    std::exit(EXIT_FAILURE);  
}  
  
struct A {  
    // Explicit noexcept overrides implicit exception specification  
    ~A() noexcept(false) {  
        throw 1;  
    }  
};  
  
struct B : public A {  
    // Compiler-generated ~B() definition inherits noexcept(false)  
    ~B() = default;  
};  
  
struct C {  
    // By default, the compiler generates an implicit noexcept(true)  
    // specifier for this user-defined destructor. To enable it to  
    // throw an exception, use an explicit noexcept(false) specifier,  
    // or compile by using /Zc:implicitNoexcept-  
    ~C() {    
        throw 1; // C4297, calls std::terminate() at run time  
    }  
};  
  
struct D : public C {  
    // This destructor gets the implicit specifier of its base.  
    ~D() = default;  
};  
  
int main()  
{  
    std::set_terminate(my_terminate);  
  
    try  
    {  
        {  
            B b;   
        }  
    }  
    catch (...)  
    {  
        // exception should reach here in all cases  
        std::cout << "~B Exception caught" << std::endl;  
    }  
    try  
    {  
        {  
            D d;  
        }  
    }  
    catch (...)  
    {  
        // exception should not reach here if /Zc:implicitNoexcept  
        std::cout << "~D Exception caught" << std::endl;  
    }  
    std::cout << "Exit returning EXIT_SUCCESS" << std::endl;  
    return EXIT_SUCCESS;  
}  
  
```  
  
 Lors de la compilation à l'aide du paramètre par défaut **\/Zc:implicitNoexcept**, l'exemple génère la sortie :  
  
  **~B Exception caught**  
**Unexpected throw caused std::terminate**  
**Exit returning EXIT\_FAILURE** Lors de la compilation à l'aide du paramètre **\/Zc:implicitNoexcept\-**, l'exemple génère la sortie :  
  
  **~B Exception caught**  
**~D Exception caught**  
**Exit returning EXIT\_SUCCESS** Pour plus d'informations sur les problèmes de conformité dans Visual C\+\+, consultez [Comportement non standard](../../cpp/nonstandard-behavior.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Modifiez la propriété **Options supplémentaires** pour inclure **\/Zc:implicitNoexcept** ou **\/Zc:implicitNoexcept\-**, puis choisissez **OK**.  
  
## Voir aussi  
 [\/Zc \(Conformité\)](../../build/reference/zc-conformance.md)   
 [noexcept](../../cpp/noexcept-cpp.md)   
 [Spécifications d'exception \(throw\)](../../cpp/exception-specifications-throw-cpp.md)   
 [terminate](../Topic/terminate%20\(%3Cexception%3E\).md)