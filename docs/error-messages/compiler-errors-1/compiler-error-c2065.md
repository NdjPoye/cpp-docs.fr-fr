---
title: Erreur du compilateur C2065 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2065
dev_langs:
- C++
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
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
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 5a3a0d4389a958f421f23a4dc96a395eaf3e22ab
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-error-c2065"></a>Erreur du compilateur C2065
'identificateur' : identificateur non déclaré  
  
Le compilateur ne peut pas trouver la déclaration d’un identificateur. Si l’identificateur est une variable, vous devez spécifier le type de la variable dans une déclaration avant de pouvoir être utilisé. Si l’identificateur est un nom de fonction, les paramètres de la fonction est obligatoire dans une déclaration avant de pouvoir utiliser la fonction. Si l’identificateur est la balise pour un type défini par l’utilisateur, par exemple, un `class` ou `struct`, le type de la balise doit être déclaré avant de pouvoir être utilisé. Si l’identificateur est un alias de type, le type doit être déclaré à l’aide un `using` déclaration ou `typedef` avant que le type peut être utilisé.  
  
Il existe de nombreuses causes possibles de cette erreur. Voici quelques-uns des problèmes plus courants :
  
## <a name="example-misspelled-identifier"></a>Exemple : identificateur de mal orthographié  
  
Cette erreur se produit généralement lorsque le nom d’identificateur est mal orthographié ou l’identificateur utilise les lettres majuscules et minuscules incorrects. Le nom dans la déclaration doit correspondre exactement au nom que vous utilisez.  
  
```cpp  
// C2065_spell.cpp  
// compile with: cl /EHsc C2065_spell.cpp 
#include <iostream> 
using namespace std; 
int main() { 
    int someIdentifier = 42; 
    cout << "Some Identifier: " << SomeIdentifier << endl;   
    // C2065: 'SomeIdentifier': undeclared identifier 
    // To fix, correct the spelling:  
    // cout << "Some Identifier: " << someIdentifier << endl;   
}  
```
  
## <a name="example-missing-header-file"></a>Exemple : le fichier d’en-tête est introuvable  
  
Vous n’avez pas inclus le fichier d’en-tête qui déclare l’identificateur. Assurez-vous que le fichier qui contient la déclaration de l’identificateur est inclus dans chaque fichier source qui l’utilise.  
  
```cpp  
// C2065_header.cpp  
// compile with: cl /EHsc C2065_spell.cpp 

//#include <stdio.h> 
int main() { 
    fpos_t file_position = 42; // C2065: 'fpos_t': undeclared identifier 
    // To fix, uncomment the #include <stdio.h> line
    // to include the header where fpos_t is defined  
} 
```  
  
Vous pouvez voir cette erreur dans les fichiers source de l’application bureau Windows si vous définissez `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN`, ou `WIN32_EXTRA_LEAN`. Ces macros de préprocesseur exclure des fichiers d’en-tête de windows.h et afxv\_w32.h pour accélérer compile. Recherchez dans windows.h et afxv_w32.h une description à jour de ce qui est exclu.  
  
## <a name="eample-missing-closing-quote"></a>Eample : le guillemet fermant manquant  
  
Cette erreur peut se produire si un guillemet fermant est manquant après une constante de chaîne. Il s’agit d’un moyen facile de confondre le compilateur. 
  
```cpp  
// C2065_quote.cpp  
// compile with: cl /EHsc C2065_quote.cpp 
#include <iostream>  

int main() { 
    // Fix this issue by adding the closing quote to "Aaaa"
    char * first = "Aaaa, * last = "Zeee"; 
    std::cout << "Name: " << first 
        << " " << last << std::endl; // C2065: 'last': undeclared identifier 
} 
```  
  
## <a name="example-use-iterator-outside-for-loop-scope"></a>Exemple : utiliser itérateur en dehors de la portée de la boucle  
  
Cette erreur peut se produire si vous déclarez une variable d’itérateur dans un `for` boucle et que vous essayez d’utiliser cette variable d’itérateur en dehors de la `for` boucle. Le compilateur permet la [/Zc : forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) option du compilateur par défaut. Consultez [prise en charge itérateur débogage](../../standard-library/debug-iterator-support.md) pour plus d’informations.  
  
```cpp  
// C2065_iter.cpp  
// compile with: cl /EHsc C2065_iter.cpp 
#include <iostream> 
#include <string> 

int main() {
    // char last = '!'; 
    std::string letters{ "ABCDEFGHIJKLMNOPQRSTUVWXYZ" }; 
    for (const char& c : letters) {
        if ('Q' == c) {
            std::cout << "Found Q!" << std::endl;
        }
        // last = c;
    }
    std::cout << "Last letter was " << c << std::endl; // C2065
    // Fix by using a variable declared in an outer scope.
    // Uncomment the lines that declare and use 'last' for an example.
    // std::cout << "Last letter was " << last << std::endl; // C2065
} 
```  
  
## <a name="example-preprocessor-removed-declaration"></a>Exemple : déclaration de suppression du préprocesseur  
  
Cette erreur peut se produire si vous faites référence à une fonction ou une variable qui est dans le code compilé conditionnellement qui n’est pas compilé de votre configuration actuelle. Cela peut également se produire si vous appelez une fonction dans un fichier d’en-tête qui n’est actuellement pas pris en charge dans votre environnement de génération. Si certaines variables ou des fonctions disponibles uniquement lors de la définition de préprocesseur ou macro, assurez-vous que le code qui appelle ces fonctions peut uniquement être compilé lors de la définition de la macro de préprocesseur même. Ce problème est facile à détecter dans l’IDE, car la déclaration de la fonction est grisée si les macros de préprocesseur requis ne sont pas définis pour la configuration de build actuelle.  
  
Il s’agit d’un exemple de code qui fonctionne lorsque vous générez en mode débogage, mais pas de la vente au détail :  
  
```cpp  
// C2065_defined.cpp
// Compile with: cl /EHsc /W4 /MT C2065_defined.cpp
#include <iostream>
#include <crtdbg.h>
#ifdef _DEBUG
    _CrtMemState oldstate;
#endif
int main() {
    _CrtMemDumpStatistics(&oldstate); 
    std::cout << "Total count " << oldstate.lTotalCount; // C2065
    // Fix by guarding references the same way as the declaration:
    // #ifdef _DEBUG
    //    std::cout << "Total count " << oldstate.lTotalCount;
    // #endif
}
```
  
## <a name="example-use-an-unscoped-identifier"></a>Exemple : utilisation d’un identificateur délimité  
  
Cette erreur peut se produire si votre identificateur n’est pas correctement étendue. Par exemple, lorsque les fonctions de bibliothèque Standard C++ et les opérateurs ne sont pas entièrement qualifiés par espace de noms, ou vous n’avez pas mis le `std` espace de noms dans la portée actuelle en utilisant un `using` directive, le compilateur ne peut pas trouver les. Pour résoudre ce problème, vous devez entièrement qualifier les noms d’identificateur, ou spécifiez l’espace de noms avec la `using` la directive.  
  
Cet exemple ne parvient pas à compiler, car `cout` et `endl` sont définies dans le `std` espace de noms :  
  
```cpp  
// C2065_scope.cpp  
// compile with: cl /EHsc C2065_scope.cpp 
// using namespace std;   // Uncomment this line to fix  
#include <iostream>  
int main() {  
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier 
                               // C2065 'endl': undeclared identifier
    // Or try the following line instead  
    std::cout << "Hello" << std::endl;  
}
```  
  
Les identificateurs qui sont déclarés à l’intérieur de `class`, `struct`, ou `enum class` types, doit également être qualifié par le nom de la portée englobante.
  
## <a name="example-ccli-type-deduction-failure"></a>Exemple : C + c++ / Échec de déduction de type CLI  
  
Cette erreur peut se produire lors de l’appel d’une fonction générique, si l’argument de type prévu ne peut pas être déduit des paramètres utilisés. Pour plus d’informations, consultez [des fonctions génériques (C + c++ / CLI)](../../windows/generic-functions-cpp-cli.md).  
  
```cpp  
// C2065_b.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
int main() {  
   // global generic function call  
   G<T>(10);   // C2065  
   G<int>(10);   // OK - fix with a specific type argument  
}  
```  
  
## <a name="example-ccli-attribute-parameters"></a>Exemple : C + c++ / Paramètres d’attribut CLI  
  
Cette erreur peut également être due à la mise en conformité du compilateur pour Visual C++ 2005 : vérification des paramètres des attributs Visual C++.  
  
```cpp  
// C2065_attributes.cpp  
// compile with: cl /c /clr C2065_attributes.cpp  
[module(DLL, name=MyLibrary)];   // C2065  
// try the following line instead  
// [module(dll, name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  

