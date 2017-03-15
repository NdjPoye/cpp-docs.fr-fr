---
title: "Fonctions inline (C++) | Microsoft Docs"
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
  - "__forceinline_cpp"
  - "__inline_cpp"
  - "inline_cpp"
  - "__forceinline"
  - "__inline"
  - "inline"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonctions inline, membres de classe"
ms.assetid: 355f120c-2847-4608-ac04-8dda18ffe10c
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonctions inline (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une fonction définie dans le corps d'une déclaration de classe est une fonction inline.  
  
## Exemple  
 Dans la déclaration de classe suivante, le constructeur `Account` est une fonction inline.  Les fonctions membres `GetBalance`, `Deposit` et `Withdraw` ne sont pas spécifiées comme **inline** mais peuvent être implémentées comme fonctions inline.  
  
```  
// Inline_Member_Functions.cpp  
class Account  
{  
public:  
    Account(double initial_balance) { balance = initial_balance; }  
    double GetBalance();  
    double Deposit( double Amount );  
    double Withdraw( double Amount );  
private:  
    double balance;  
};  
  
inline double Account::GetBalance()  
{  
    return balance;  
}  
  
inline double Account::Deposit( double Amount )  
{  
    return ( balance += Amount );  
}  
  
inline double Account::Withdraw( double Amount )  
{  
    return ( balance -= Amount );  
}  
int main()  
{  
}  
```  
  
> [!NOTE]
>  Dans la déclaration de classe, les fonctions ont été déclarées sans mot clé **inline**.  Le mot clé **inline** peut être spécifié dans la déclaration de classe. Le résultat est identique.  
  
 Une fonction membre inline donnée doit être déclarée de la même manière dans chaque unité de compilation.  Cette contrainte entraîne les fonctions inline à se comporter comme si elles étaient des fonctions instanciées.  En outre, il doit exister une seule définition d'une fonction inline.  
  
 Une fonction membre de classe correspond par défaut à une liaison externe sauf qu'une définition de cette fonction contient le spécificateur **inline**.  L'exemple précédent indique que ces fonctions n'ont pas besoin d'être déclarées explicitement avec le spécificateur **inline**. L'utilisation d'**inline** dans la définition de fonction transforme la fonction en fonction inline.  Toutefois, il n'est pas conforme de redéclarer une fonction comme **inline** après un appel à cette fonction.  
  
## Inline, \_\_inline et \_\_forceinline  
 Les spécificateurs `inline` et `__inline` indiquent au compilateur d'insérer une copie du corps de la fonction dans chaque emplacement où la fonction est appelée.  
  
 L'insertion \(appelée expansion inline ou incorporation\) se produit uniquement si l'analyse des coûts\-avantages du compilateur montre qu'elle est rentable.  L'expansion inline allège la surcharge des appels de fonction au coût potentiel d'une plus grande taille de code.  
  
 Le mot clé `__forceinline` substitue l'analyse des coûts\-avantages et se base sur le jugement du programmeur à la place.  Soyez prudent lorsque vous utilisez `__forceinline`.  L'utilisation sans discernement de `__forceinline` peut entraîner un code plus volumineux avec seulement des gains de performance marginaux ou, dans certains cas, des pertes de performance \(causées par exemple par une pagination accrue d'un fichier exécutable plus volumineux\).  
  
 L'utilisation des fonctions inline permet accélérer l'exécution de votre programme, car celles\-ci éliminent la surcharge associée aux appels de fonction.  Les fonctions développées inline sont soumises à des optimisations de code non disponibles pour les fonctions normales.  
  
 Le compilateur traite les options d'expansion inline et les mots clés comme des suggestions.  Rien ne garantit que les fonctions seront incorporées.  Vous ne pouvez pas forcer le compilateur à incorporer une fonction particulière, même avec le mot clé `__forceinline`.  Lors de la compilation avec **\/clr**, le compilateur n'incorpore pas une fonction si des attributs de sécurité lui sont appliqués.  
  
 Le mot clé **inline** est disponible uniquement en C\+\+.  Les mots clés `__inline` et `__forceinline` sont disponibles à la fois en C et C\+\+.  Pour assurer la compatibilité avec les versions antérieures, **\_inline** est un synonyme de `__inline`.  
  
 Le mot clé **inline** indique au compilateur que l'expansion inline est recommandée.  Toutefois, le compilateur peut créer une instance séparée de la fonction \(instanciation\) et créer des liaisons d'appel standard au lieu d'insérer le code inline.  Les deux cas où cela peut se produire sont :  
  
-   Fonctions récursives.  
  
-   Fonctions référencées par l'intermédiaire d'un pointeur ailleurs dans l'unité de traduction.  
  
 Ces raisons peuvent interférer avec l'incorporation, *comme le peuvent d'autres*, à la discrétion du compilateur ; vous ne devez pas dépendre du spécificateur **inline** pour qu'une fonction soit incorporée.  
  
 Comme avec les fonctions normales, il n'existe aucun ordre défini d'évaluation des arguments d'une fonction inline.  En pratique, il peut être différent de l'ordre dans lequel les arguments sont évalués lorsqu'ils sont passés à l'aide d'un protocole d'appel de fonction normal.  
  
 L'option d'optimisation du compilateur [\/Ob](../build/reference/ob-inline-function-expansion.md) aide à déterminer si l'expansion de fonction inline se produit réellement.  
  
 [\/LTCG](../build/reference/ltcg-link-time-code-generation.md) effectue une incorporation entre modules, qu'elle ait été demandée ou non dans le code source.  
  
### Exemple 1  
  
```  
// inline_keyword1.cpp  
// compile with: /c  
inline int max( int a , int b ) {  
   if( a > b )   
      return a;  
   return b;  
}  
```  
  
 Les fonctions membres d'une classe peuvent être déclarées inline en utilisant le mot clé **inline** ou en plaçant la définition de la fonction dans la définition de la classe.  
  
### Exemple 2  
  
```  
// inline_keyword2.cpp  
// compile with: /EHsc /c  
#include <iostream>  
using namespace std;  
  
class MyClass {  
public:  
   void print() { cout << i << ' '; }   // Implicitly inline  
private:  
   int i;  
};  
```  
  
### Section spécifique à Microsoft  
 Le mot clé `__inline` est équivalent à **inline**.  
  
 Même avec `__forceinline`, le compilateur ne peut pas incorporer le code dans toutes les circonstances.  Le compilateur ne peut pas incorporer une fonction dans les cas suivants :  
  
-   La fonction ou son appelant est compilé avec \/Ob0 \(option par défaut pour les versions debug\).  
  
-   La fonction et l'appelant utilisent différents types de gestion des exceptions \(gestion des exceptions C\+\+ dans l'un, gestion structurée des exceptions dans l'autre\).  
  
-   La fonction a une liste d'arguments variable.  
  
-   La fonction utilise l'assembly inline, sauf si elle est compilée avec \/Og, \/Ox, \/O1 ou \/O2.  
  
-   La fonction est récursive et non accompagnée de **\#pragma inline\_recursion\(on\)**.  Avec le pragma, les fonctions récursives sont incorporées à une profondeur par défaut de 16 appels.  Pour réduire la profondeur d'incorporation, utilisez le pragma [inline\_depth](../preprocessor/inline-depth.md).  
  
-   La fonction est virtuelle et est appelée virtuellement.  Les appels directs aux fonctions virtuelles peuvent être incorporés.  
  
-   Le programme prend l'adresse de la fonction et l'appel est effectué via le pointeur vers la fonction.  Les appels directs aux fonctions dont l'adresse est acceptée peuvent être incorporés.  
  
-   La fonction est également marquée avec le modificateur [naked](../cpp/naked-cpp.md) [\_\_declspec](../cpp/declspec.md).  
  
 Si le compilateur ne peut pas incorporer une fonction déclarée avec `__forceinline`, il génère un avertissement de niveau 1.  
  
 Les fonctions récursives peuvent être substituées inline à une profondeur spécifiée par le pragma [inline\_depth](../preprocessor/inline-depth.md), pouvant atteindre 16 appels au maximum.  Au\-delà de cette profondeur, les appels de fonction récursive sont traités comme des appels à une instance de la fonction.  La profondeur à laquelle les fonctions récursives sont examinées par l'heuristique inline ne peut pas dépasser 16.  Le pragma [inline\_recursion](../preprocessor/inline-recursion.md) contrôle l'expansion inline d'une fonction en cours d'expansion.  Pour des informations connexes, consultez l'option du compilateur \(\/Ob\) [Expansion des fonctions inline](../build/reference/ob-inline-function-expansion.md).  
  
### FIN de la section spécifique à Microsoft  
 Pour plus d'informations sur l'utilisation du spécificateur **inline**, consultez :  
  
-   [Fonctions membres des classes inline](../cpp/inline-functions-cpp.md)  
  
-   [Fonctions inline et macros](../misc/inline-functions-versus-macros.md)  
  
-   [Quand utiliser les fonctions inline](../misc/when-to-use-inline-functions.md)  
  
-   [Définition de fonctions C\+\+ incorporées avec dllexport et dllimport](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)  
  
## Quand utiliser les fonctions inline  
 Les fonctions inline sont utilisées de façon optimale pour les petites fonctions telles que l'accès aux membres de données privées.  L'objectif principal de ces fonctions d'accesseur à une ou deux lignes est de retourner des informations d'état sur les objets. Les fonctions courtes sont sensibles aux charges mémoire des appels de fonction.  Les fonctions longues passent proportionnellement moins de temps dans la séquence d'appel\/retour et bénéficient moins de l'inlining.  
  
 La classe `Point`, introduite dans [Résultats de l'appel de fonction](../misc/function-call-results.md) peut être optimisée comme suit :  
  
```  
// when_to_use_inline_functions.cpp  
class Point  
{  
public:  
    // Define "accessor" functions as  
    //  reference types.  
    unsigned& x();  
    unsigned& y();  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
inline unsigned& Point::x()  
{  
    return _x;  
}  
inline unsigned& Point::y()  
{  
    return _y;  
}  
int main()  
{  
}  
```  
  
 Si la manipulation des coordonnées est une opération relativement courante dans un client de cette classe, la spécification des deux fonctions d'accesseur \(`x` et `y` dans l'exemple précédent\) comme **inline** stocke généralement la charge sur :  
  
-   Appels de fonction \(notamment le paramètre passe et place l'adresse de l'objet dans la pile\)  
  
-   Conservation du frame de pile de l'appelant  
  
-   Nouvelle installation du frame de pile  
  
-   Communication de la valeur de retour  
  
-   Restauration de l'ancien frame de pile  
  
-   Retourner  
  
## Fonctions inline etmacros  
 Bien que les fonctions inline soient similaires aux macros \(car le code de fonction est développé au point de l'appel au moment de la compilation\), les fonctions inline sont analysées par le compilateur, alors que les macros sont développées par le préprocesseur.  Par conséquent, il existe plusieurs différences importantes :  
  
-   Les fonctions inline suivent tous les protocoles de sécurité de type appliqués sur les fonctions normales.  
  
-   Les fonctions inline sont spécifiées à l'aide de la même syntaxe comme toute autre fonction, mais elles incluent le mot clé **inline** dans la déclaration de fonction.  
  
-   Les expressions passées comme arguments aux fonctions inline sont évaluées une fois.  Dans certains cas, les expressions passées comme arguments aux macros peuvent être évaluées plusieurs fois.  
  
 L'exemple suivant montre une macro qui convertit les minuscules en majuscules :  
  
```  
// inline_functions_macro.c  
#include <stdio.h>  
#include <conio.h>  
  
#define toupper(a) ((a) >= 'a' && ((a) <= 'z') ? ((a)-('a'-'A')):(a))  
  
int main() {  
   char ch;  
   printf_s("Enter a character: ");  
   ch = toupper( getc(stdin) );  
   printf_s( "%c", ch );  
}  
//  Sample Input:  xyz  
// Sample Output:  Z  
  
```  
  
 L'objectif de l'expression `toupper(getc(stdin))` est qu'un caractère doit être lu à partir du périphérique de console \(`stdin`\) et, si nécessaire, être converti en majuscules.  
  
 Grâce à l'implémentation de la macro, `getc` est exécuté une fois pour déterminer si le caractère est supérieur ou égal à « a », et une fois pour déterminer s'il est inférieur ou égal à « z ». S'il est dans cette plage, `getc` est à nouveau exécuté pour convertir le caractère en majuscules.  Cela signifie que le programme attend deux ou trois caractères lorsque, idéalement, il doit en attendre qu'un seul.  
  
 Les fonctions inline remédient au problème décrit auparavant :  
  
```  
// inline_functions_inline.cpp  
#include <stdio.h>  
#include <conio.h>  
  
inline char toupper( char a ) {  
   return ((a >= 'a' && a <= 'z') ? a-('a'-'A') : a );  
}  
  
int main() {  
   printf_s("Enter a character: ");  
   char ch = toupper( getc(stdin) );  
   printf_s( "%c", ch );  
}  
```  
  
  **Exemple d'entrée : `a`**   
 **Résultat de l'exemple : `A`**    
## Voir aussi  
 [noinline](../cpp/noinline.md)   
 [auto\_inline](../preprocessor/auto-inline.md)