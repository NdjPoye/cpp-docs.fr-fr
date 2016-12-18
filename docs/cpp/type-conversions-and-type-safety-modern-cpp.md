---
title: "Conversions de types et s&#233;curit&#233; de type (Modern C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 629b361a-2ce1-4700-8b5d-ab4f57b245d5
caps.latest.revision: 23
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conversions de types et s&#233;curit&#233; de type (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce document identifie les problèmes courants de conversion de type et décrit la façon de les éviter dans votre code C\+\+.  
  
 Lorsque vous écrivez un programme en C\+\+, il est important de vérifier qu'il est de type sécurisé.  Cela signifie que chaque variable, argument de fonction, et valeur de retour de fonction enregistre un type acceptable de données, et que les opérations qui impliquent des valeurs de types différents aient du sens et n'entraînent pas une perte de données, une interprétation incorrecte des modèles binaires, ou une corruption de la mémoire.  Un programme qui ne convertit jamais explicitement ou implicitement des valeurs d'un type à un autre est de type sécurisé par définition.  Toutefois, des conversions de type, même des conversions non sécurisées, sont parfois requises.  Par exemple, vous pouvez devoir stocker le résultat d'une opération à virgule flottante dans une variable de type `int`, ou vous devrez peut\-être passer la valeur d'un `int` non signé à une fonction qui prend un `int`signé.  Les deux exemples illustrent des conversions non sécurisées car elles peuvent provoquer une perte de données ou la réinterprétation d'une valeur.  
  
 Lorsque le compilateur détecte une conversion non sécurisée, il émet une erreur ou un avertissement.  Une erreur arrête la compilation ; un avertissement permet à la compilation de continuer mais indique une erreur possible dans le code.  Toutefois, même si votre programme compile sans avertissements, il peut toujours contenir du code conduisant à des conversions de type implicites qui produisent des résultats incorrects.  Les erreurs de type peuvent également être introduites par des conversions explicites, ou des casts dans le code.  
  
## Conversions de type implicites  
 Lorsqu'une expression contient des opérandes de types intégrés différents, et qu'aucun cast explicite n'est présent, le compilateur utilise des *conversions standards* intégrées afin de convertir un des opérandes pour que les types correspondent.  Le compilateur essaie les conversions dans une séquence bien définie jusqu'à ce qu'une réussisse.  Si la conversion sélectionnée est une promotion, le compilateur ne génère pas d'avertissement.  Si la conversion se rétrécit, le compilateur émet un avertissement concernant une perte possible de données.  La perte réelle de données se produit ou non suivant les valeurs réelles concernées, mais nous vous recommandons traiter cet avertissement comme une erreur.  Si un type défini par l'utilisateur est défini, le compilateur tente d'utiliser les conversions spécifiées dans la définition de la classe.  Si elle ne peut pas trouver une conversion acceptable, le compilateur génère une erreur et ne compile pas le programme.  Pour plus d'informations sur les règles qui régissent les conversions standards, consultez [Conversions standard](../cpp/standard-conversions.md).  Pour plus d'informations sur les conversions définies par l'utilisateur, consultez [Conversions définies par l'utilisateur](../dotnet/user-defined-conversions-cpp-cli.md).  
  
### Conversions étendues \(promotion\)  
 Dans une conversion étendue, une valeur dans une variable plus petite est assignée à une variable plus grande sans perte de données.  Comme les conversions étendues sont toujours sécurisées, le compilateur les exécute silencieusement et n'émet pas d'avertissement.  Les conversions suivantes sont des conversions étendues.  
  
|From|Pour|  
|----------|----------|  
|Tout type intégral signé ou non signé sauf `long long` ou `__int64`|`double`|  
|`bool` ou `char`|Tout autre type intégré|  
|`short` ou `wchar_t`|`int`, `long`, `long long`|  
|`int`, `long`|`long long`|  
|`float`|`double`|  
  
### Conversions restrictives \(contrainte\)  
 Le compilateur exécute des conversions restrictives implicitement, mais vous avertit de la perte de données possible.  Prenez ces avertissements très au sérieux.  Si vous êtes certain qu'aucune perte de données n'aura lieu puisque les valeurs de la variable plus grande s'ajusteront toujours dans la variable plus petite, puis ajoutez un cast explicite afin que le compilateur n'émette plus d'avertissement.  Si vous n'êtes pas sûr que la conversion est sécurisée, ajoutez à votre code un certain type de contrôle d'exécution pour gérer la perte possible de données afin que votre programme ne produise pas de résultats incorrects.  Pour obtenir des suggestions sur la gestion de ce scénario, consultez [\(NOTINBUILD\)How to: Handle Narrowing Conversions \(C\+\+\)](http://msdn.microsoft.com/fr-fr/e483237e-501e-4a12-ac24-51526f6ddeaa).  
  
 Toute conversion d'un type à virgule flottante vers un type intégral est une conversion restrictive car la partie fractionnaire de la valeur à virgule flottante est ignorée et perdue.  
  
 L'exemple de code suivant montre quelques conversions restrictives implicites, et les avertissements que le compilateur émet les concernant.  
  
```cpp  
  
int i = INT_MAX + 1; //warning C4307:'+':integral constant overflow  
wchar_t wch = 'A'; //OK  
char c = wch; // warning C4244:'initializing':conversion from 'wchar_t'  
              // to 'char', possible loss of data  
unsigned char c2 = 0xfffe; //warning C4305:'initializing':truncation from  
                           // 'int' to 'unsigned char'  
int j = 1.9f; // warning C4244:'initializing':conversion from 'float' to  
              // 'int', possible loss of data  
int k = 7.7; // warning C4244:'initializing':conversion from 'double' to  
             // 'int', possible loss of data  
  
```  
  
### Signé \- conversions non signées  
 Un type intégral signé et son équivalent non signé sont toujours de la même taille, mais ils diffèrent dans la façon dont le modèle binaire est interprété pour la transformation de la valeur.  L'exemple de code suivant illustre ce qui se produit lorsque le même modèle binaire est interprété comme une valeur signée et comme une valeur non signée.  Le modèle binaire stocké dans `num` et `num2` ne change jamais de ce qui est affiché dans l'illustration précédente.  
  
```cpp  
  
using namespace std;  
unsigned short num = numeric_limits<unsigned short>::max(); // #include <limits>  
short num2 = num;  
cout << "unsigned val = " << num << " signed val = " << num2 << endl;  
// Prints: unsigned val = 65535 signed val = -1  
  
// Go the other way.  
num2 = -1;  
num = num2;  
cout << "unsigned val = " << num << " signed val = " << num2 << endl;  
// Prints: unsigned val = 65535 signed val = -1  
  
```  
  
 Notez que les valeurs sont réinterprétées dans les deux directions.  Si votre programme produit des résultats étranges dans lesquels le signe de la valeur est inversé par rapport à ceux attendus, recherchez les conversions implicites entre les types intégraux signés et non signés.  Dans l'exemple suivant, le résultat de l'expression \(0 – 1\) est implicitement converti d'un `int` à un `unsigned int` lorsque enregistré dans `num`.  Cela entraîne une réinterprétation du modèle binaire.  
  
```cpp  
  
unsigned int u3 = 0 - 1;  
cout << u3 << endl; // prints 4294967295  
  
```  
  
 Le compilateur ne prévient pas à propos de conversions implicites entre des types intégraux signés et non signés.  Par conséquent, nous vous recommandons d'éviter entièrement les conversions de signé à non\-signé.  Si vous ne pouvez pas les éviter, alors ajoutez à votre code un contrôle d'exécution pour détecter si la valeur convertie est supérieure ou égale à zéro et inférieure ou égale à la valeur maximale du type signé.  Les valeurs dans cette plage seront transférer de signé à non\-signé ou de non\-signé à signé sans être réinterprétées.  
  
### Conversions de pointeurs  
 Dans beaucoup d'expressions, le tableau de style C est implicitement converti en un pointeur vers le premier élément du tableau, et les conversions constantes peuvent se produire en silence.  Bien qu'il soit pratique, il est également potentiellement sujet aux erreurs.  Par exemple, l'exemple de code mal conçu suivant apparaît absurde, mais il compile pourtant dans Visual C\+\+ et produit un résultat « p ».  D'abord, le littéral constant de chaîne « Aide » est converti en `char*` qui indique le premier élément du tableau ; ce pointeur est ensuite incrémenté par trois éléments afin qu'il pointe désormais vers le dernier élément « p ».  
  
```cpp  
  
char* s = "Help" + 3;  
  
```  
  
## Conversions explicites \(casts\)  
 En utilisant une opération cast, vous pouvez demander au compilateur de convertir une valeur d'un type à un autre.  Le compilateur générera une erreur dans certains cas si les deux types sont complètement non liés, mais dans d'autres cas il ne lève pas d'erreur même si l'opération n'est pas de type sécurisé.  Utilisez les casts avec modération car toute conversion d'un type à un autre est une source potentielle d'erreur de programmation.  Toutefois, les casts sont parfois obligatoires, et tous les casts ne sont pas tous aussi dangereux les uns que les autres.  Une utilisation efficace d'un cast est lorsque votre code exécute une conversion restrictive et que vous savez que la conversion ne provoque pas la création de résultats incorrects par votre programme.  En effet, cela indique au compilateur que vous savez que vous faites et arrêter de vous tracasser avec les avertissements le concernant.  Une autre utilisation est de passer d'une classe pointeur\-à\-dérivée à une classe pointeur\-à\-base.  Une autre utilisation est de faire disparaître le ness `const` d'une variable pour le passer à une fonction qui requiert un argument non `const`.  La plupart de ces opérations cast impliquent un risque.  
  
 En programmation de style C, l'opérateur cast de même style C est utilisé pour tous les types de casts.  
  
```cpp  
  
(int) x; // old-style cast, old-style syntax  
int(x); // old-style cast, functional syntax  
  
```  
  
 L'opérateur de cast de style C est identique à l'opérateur d'appel \(\) et est par conséquent inaperçu dans le code et facile à cerner.  Tous deux sont mauvais car il est difficile de le reconnaître au premier regard ou de le chercher, et elles sont assez différentes pour appeler toute combinaison de `static`, `const`, et `reinterpret_cast`.  Comprendre ce qu'est un cast à l'ancienne fait réellement peut être difficile et sujet aux erreurs.  Pour toutes ces raisons, lorsqu'un cast requis, nous vous recommandons d'utiliser un des opérateurs cast de conversion en C\+\+ suivants, qui sont dans certains cas de type plus sécurisé, et qui expriment beaucoup plus explicitement l'intention de programmation :  
  
-   `static_cast`, pour les casts qui sont activés au moment de la compilation uniquement.  `static_cast` retourne une erreur si le compilateur détecte que vous essayez d'utiliser des casts entre des types qui sont complètement incompatibles.  Vous pouvez également l'utiliser pour un cast entre un pointeur vers base et un pointeur vers dérivé, mais le compilateur ne peut pas toujours indiquer si ces conversions seront sécurisées au moment de l'exécution.  
  
    ```cpp  
  
    double d = 1.58947;  
    int i = d;  // warning C4244 possible loss of data  
    int j = static_cast<int>(d);       // No warning.  
    string s = static_cast<string>(d); // Error C2440:cannot convert from  
                                       // double to std:string  
  
    // No error but not necessarily safe.  
    Base* b = new Base();  
    Derived* d2 = static_cast<Derived*>(b);  
  
    ```  
  
     Pour plus d'informations, consultez [static\_cast](../cpp/static-cast-operator.md).  
  
-   `dynamic_cast`, pour la sécurité, des casts de pointeur vers base à pointeur vers dérivé qui sont vérifiés au runtime.  `dynamic_cast` est plus sécurisé que `static_cast` pour les downcasts, mais le contrôle d'exécution entraîne une certaine charge supplémentaire.  
  
    ```cpp  
  
    Base* b = new Base();  
  
    // Run-time check to determine whether b is actually a Derived*  
    Derived* d3 = dynamic_cast<Derived*>(b);  
  
    // If b was originally a Derived*, then d3 is a valid pointer.  
    if(d3)  
    {  
       // Safe to call Derived method.  
       cout << d3->DoSomethingMore() << endl;  
    }  
    else  
    {  
       // Run-time check failed.  
       cout << "d3 is null" << endl;  
    }  
  
    //Output: d3 is null;  
  
    ```  
  
     Pour plus d'informations, consultez [dynamic\_cast](../cpp/dynamic-cast-operator.md).  
  
-   `const_cast`, pour enlever la caractéristique `const` d'une variable, ou convertir une variable non `const` en une variable `const`.  Enlever l'attribut `const` par casting en utilisant cet opérateur est tout aussi susceptible de provoquer des erreurs que d'utiliser un casting C. Toutefois, avec `const-cast` vous aurez moins de risque d'effectuer ce cast par erreur.  Vous devrez parfois enlever l'attribut `const` d'une variable par un cast, par exemple pour passer une variable `const` à une fonction qui prend un paramètre non `const`.  L'exemple suivant montre comment effectuer cette opération.  
  
    ```cpp  
  
    void Func(double& d) { ... }  
    void ConstCast()  
    {  
       const double pi = 3.14;  
       Func(const_cast<double&>(pi)); //No error.  
    }  
  
    ```  
  
     Pour plus d'informations, consultez [const\_cast](../cpp/const-cast-operator.md).  
  
-   `reinterpret_cast`, pour des casts entre des types non liés comme `pointer` vers `int`.  
  
    > [!NOTE]
    >  Cet opérateur de cast n'est pas utilisé aussi souvent que les autres, et il n'est pas garanti d'être applicable à d'autres compilateurs.  
  
     L'exemple suivant montre comment un `reinterpret_cast` diffère d'un `static_cast`.  
  
    ```cpp  
  
    const char* str = "hello";  
    int i = static_cast<int>(str);//error C2440: 'static_cast' : cannot  
                                  // convert from 'const char *' to 'int'  
    int j = (int)str; // C-style cast. Did the programmer really intend  
                      // to do this?  
    int k = reinterpret_cast<int>(str);// Programming intent is clear.  
                                       // However, it is not 64-bit safe.  
  
    ```  
  
     Pour plus d'informations, consultez [reinterpret\_cast, opérateur](../cpp/reinterpret-cast-operator.md).  
  
## Voir aussi  
 [Système de type C\+\+](../cpp/cpp-type-system-modern-cpp.md)   
 [Bienvenue dans C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)