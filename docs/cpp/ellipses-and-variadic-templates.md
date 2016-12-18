---
title: "Ellipses et mod&#232;les variadiques | Microsoft Docs"
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
ms.assetid: f20967d9-c967-4fd2-b902-2bb1d5ed87e3
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ellipses et mod&#232;les variadiques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment utiliser l'ellipse \(`...`\) avec les modèles variadic C\+\+.  L'ellipse a de [nombreux usages](../misc/ellipsis-dot-dot-dot.md) dans C et C\+\+.  Ceux\-ci incluent des listes d'arguments variables pour les fonctions.  La fonction `printf()` de la bibliothèque Runtime C est l'un des exemples les plus connus.  
  
 Un *modèle variadique* est une classe ou un modèle de fonction qui prend en charge un nombre arbitraire d'arguments.  Ce mécanisme est particulièrement utile pour les développeurs de bibliothèques C\+\+ car vous pouvez l'appliquer aux modèles de classe et aux modèles de fonction, et donc fournir une large gamme de fonctionnalités et de flexibilité de type sécurisé et non triviales.  
  
## Syntaxe  
 Un bouton de sélection est utilisé de deux façons par les modèles variadiques.  À gauche du nom de paramètre, cela signifie un *paquet de paramètre*, et à droite du nom de paramètre, cela permet d'étendre les paquets de paramètre dans des noms différents.  
  
 Voici un exemple de base de la syntaxe de définition de la *classe de modèle variadique* :  
  
```cpp  
template<typename... Arguments> class classname;  
```  
  
 Pour des packages et des expansions de paramètres, vous pouvez ajouter des espaces blancs autour des ellipses, selon votre préférence, comme indiqué dans ces exemples :  
  
```cpp  
template<typename ...Arguments> class classname;  
```  
  
 Ou comme suit :  
  
```cpp  
template<typename ... Arguments> class classname;  
```  
  
 Notez que cet article utilise la convention qui est présentée dans le premier exemple \(l'ellipses est attachée à `typename`\).  
  
 Dans les exemples précédents, `Arguments` est un package de paramètre.  La classe `classname` peut accepter un nombre d'arguments variable, comme dans les exemples suivants :  
  
```cpp  
  
template<typename... Arguments> class vtclass;  
  
vtclass< > vtinstance1;  
vtclass<int> vtinstance2;  
vtclass<float, bool> vtinstance3;  
vtclass<long, std::vector<int>, std::string> vtinstance4;  
  
```  
  
 En utilisant une définition de classe de modèle variadique, vous pouvez également exiger au moins un paramètre :  
  
```cpp  
template <typename First, typename... Rest> class classname;  
  
```  
  
 Voici un exemple de base de la syntaxe de la *fonction de modèle variadique* :  
  
```cpp  
template <typename... Arguments> returntype functionname(Arguments... args);  
```  
  
 Le package de paramètres `Arguments` est ensuite développé pour être utilisé, comme indiqué dans la section suivante, **Présentation des modèles variadiques**.  
  
 D'autres formes de syntaxe de fonction de modèle variadique sont possibles, y compris mais sans s'y limiter, les exemples suivants :  
  
```cpp  
template <typename... Arguments> returntype functionname(Arguments&... args);   
template <typename... Arguments> returntype functionname(Arguments&&... args);  
template <typename... Arguments> returntype functionname(Arguments*... args);  
```  
  
 Les spécificateurs tels que `const` sont également autorisés :  
  
```cpp  
template <typename... Arguments> returntype functionname(const Arguments&... args);  
  
```  
  
 Comme avec les définitions de classe de modèle variadique, vous pouvez concevoir des fonctions qui nécessitent au moins un paramètre :  
  
```cpp  
template <typename First, typename... Rest> returntype functionname(const First& first, const Rest&... args);  
  
```  
  
 Les modèles variadiques utilisent l'opérateur `sizeof...()` \(non lié à l'opérateur plus ancien `sizeof()`\) :  
  
```cpp  
template<typename... Arguments>  
void tfunc(const Arguments&... args)  
{  
    const unsigned numargs = sizeof...(Arguments);  
  
    X xobj[numargs]; // array of some previously defined type X  
  
    helper_func(xobj, args...);  
}  
  
```  
  
## Informations complémentaires sur le positionnement d'ellipse  
 Auparavant, cet article décrivait le positionnement de sélection qui définit des packages et des expansions de paramètre comme « à gauche du nom de paramètre, cela signifie un paquet de paramètre, et à droite du nom de paramètre, cela développe les paquets de paramètre dans des noms distincts ».  C'est techniquement vrai mais peut être ambigu dans la transposition en code.  Considérez :  
  
-   Dans une liste de paramètres de modèle \(`template <parameter-list>`\), `typename...` introduit un paquet de paramètre de modèle.  
  
-   Dans une clause de déclaration de paramètre \(`func(parameter-list)`\), des points de suspension « de niveau supérieur » présentent un paquet de paramètre de fonction, et le positionnement de sélection est important :  
  
    ```cpp  
  
    // v1 is NOT a function parameter pack:  
    template <typename... Types> void func1(std::vector<Types...> v1);   
  
    // v2 IS a function parameter pack:  
    template <typename... Types> void func2(std::vector<Types>... v2);   
    ```  
  
-   Lorsque les ellipses apparaissent immédiatement après un nom de paramètre, vous avez une expansion de pack de paramètre.  
  
## Exemple  
 Un bon moyen d'illustrer le mécanisme de fonction de modèle variadique consiste à l'utiliser dans une réécriture d'une fonctionnalité de `printf` :  
  
```cpp  
#include <iostream>  
  
using namespace std;  
  
void print() {  
    cout << endl;  
}  
  
template <typename T> void print(const T& t) {  
    cout << t << endl;  
}  
  
template <typename First, typename... Rest> void print(const First& first, const Rest&... rest) {  
    cout << first << ", ";  
    print(rest...); // recursive call using pack expansion syntax  
}  
  
int main()  
{  
    print(); // calls first overload, outputting only a newline  
    print(1); // calls second overload  
  
    // these call the third overload, the variadic template,   
    // which uses recursion as needed.  
    print(10, 20);  
    print(100, 200, 300);  
    print("first", 2, "third", 3.14159);  
}  
  
```  
  
## Sortie  
  
```  
  
1  
10, 20  
100, 200, 300  
first, 2, third, 3.14159  
```  
  
> [!NOTE]
>  La plupart des implémentations qui intègrent des fonctions de modèles variadiques utilisent la récurrence sous une forme quelconque, mais elle est légèrement différente de la récurrence classique. La récurrence classique implique qu'une fonction s'appelle en utilisant la même signature. \(Elle peut être surchargée ou modélisée, mais la même signature est choisie à chaque fois.\) La récursivité variadique implique l'appel d'un modèle de fonction variadique en utilisant des nombres d'arguments qui différent \(presque toujours décroissants\) et, de ce fait, en horodatant une signature différente à chaque fois.  Un « cas de base » est encore requis, mais la nature de la récursivité est différente.  
  
## Voir aussi  
 [Points de suspension \(...\)](../misc/ellipsis-dot-dot-dot.md)