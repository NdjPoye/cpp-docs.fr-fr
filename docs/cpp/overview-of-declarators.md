---
title: "Vue d’ensemble des déclarateurs | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declarators, about declarators
ms.assetid: 0f2e2312-80bd-4154-8345-718bd9ed2173
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 4a8f795a23f4e93f02d5d6b5ce98d60555a432d6
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="overview-of-declarators"></a>Vue d'ensemble des déclarateurs
Les déclarateurs sont les composants d'une déclaration qui spécifient les noms des objets ou des fonctions. Les déclarateurs spécifient également si l'objet nommé est un objet, un pointeur, une référence ou un tableau.  Les déclarateurs ne spécifient pas le type de base, mais ils modifient les informations de type dans le type de base pour spécifier les types dérivés, tels que des pointeurs, des références et des tableaux.  Appliqué aux fonctions, le déclarateur utilise le spécificateur de type pour spécifier complètement le type de retour d'une fonction comme étant un objet, un pointeur ou une référence. (Spécificateurs, présentés dans [déclarations et définitions](declarations-and-definitions-cpp.md), acheminent des propriétés telles que le stockage et le type de classe. Modificateurs, présentés dans cette section et dans [modificateurs spécifiques Microsoft](../cpp/microsoft-specific-modifiers.md), modifient les déclarateurs.) La figure ci-dessous illustre une déclaration complète de `MyFunction` et répertorie les composants de la déclaration.  
  
 ![Modificateurs, spécificateurs et déclarateurs](../cpp/media/vc38qy1.gif "vc38QY1")  
Spécificateurs, modificateurs et déclarateurs  
  
 **Section spécifique à Microsoft**  
  
 La plupart des mots clés étendus Microsoft peuvent être utilisés comme modificateurs pour former des types dérivés ; ce ne sont ni des spécificateurs, ni des déclarateurs. (Consultez [modificateurs spécifiques Microsoft](../cpp/microsoft-specific-modifiers.md).)  
  
 **FIN de la section spécifique à Microsoft**  
  
 Les déclarateurs figurent dans la syntaxe d'une déclaration après une liste facultative de spécificateurs. Ces spécificateurs sont présentés dans [déclarations.](declarations-and-definitions-cpp.md) Une déclaration peut contenir plusieurs déclarateurs, mais chaque déclarateur déclare un seul nom.  
  
 L'exemple de déclaration suivant indique comment les spécificateurs et les déclarateurs sont combinés pour former une déclaration complète :  
  
```  
const char *pch, ch;  
```  
  
 Dans la déclaration précédente, les mots clés **const** et `char` constituent la liste des spécificateurs. Deux déclarateurs sont répertoriés : `*pch` et `ch`.  Une déclaration qui déclare plusieurs entités se compose d'un spécificateur de type, suivi d'une liste de déclarateurs séparés par des virgules, et se termine par un point-virgule.  
  
 **Déclarateurs d’objets simples**  
  
 Le déclarateur d'un objet simple, tel qu'un objet int ou double, est simplement son nom éventuellement entre parenthèses.  
  
 `int i; // declarator is i`  
  
 `int (i); // declarator is (i)`  
  
 **Déclarateurs de pointeurs, références et tableaux**  
  
 Les opérateurs de pointeur insérés devant le nom font de l'objet un pointeur ou une référence.  Le ** \* ** opérateur déclare le nom en tant que pointeur ; la ** & ** opérateur déclare en tant que référence.  
  
```  
int *i; // declarator is *i  
int **i; // declarator is **i;  
int &i = x; // declaratory is &i  
```  
  
 L'ajout de `const` ou de `volatile` dote le pointeur de ces propriétés particulières.  L'utilisation de ces spécificateurs dans un déclarateur (par opposition à leur utilisation dans le spécificateur de type) modifie les propriétés du pointeur, pas l'objet désigné :  
  
```  
char *const cpc; // const pointer to char   
const char *pcc; // pointer to const char   
const char *const cpcc; // const pointer to const char  
```  
  
 Informations supplémentaires peuvent être disponibles dans [pointeurs const et volatile](../cpp/const-and-volatile-pointers.md).  
  
 Un pointeur désignant un membre d'une classe ou d'un struct est déclaré avec le spécificateur de nom imbriqué approprié :  
  
```  
int X::* pIntMember;   
int ::X::* pIntMember; // the initial :: specifies X is in global scope  
char Outer::Inner::* pIntMember; // pointer to char in a nested class  
```  
  
 La mise entre crochets d'une expression constante facultative après le nom définit l'objet en tant que tableau.  Les crochets suivants déclarent des dimensions supplémentaires du tableau.  
  
```  
int i[5]; // array with five elements of type int numbered from 0 to 4  
int i[]; // array of unknown size  
char *s[4]; // array of pointers to char  
int i[2][2]; // two dimensional array  
```  
  
 **Déclarateurs de fonctions**  
  
 La liste d’arguments est mise entre parenthèses après le nom pour déclarer une fonction.  L'exemple ci-dessous déclare une fonction de type de retour `int` et trois arguments de type `int`.  
  
```  
int f(int a, int b, int c);  
```  
  
 Les pointeurs et les références de fonctions sont déclarés en ajoutant l'opérateur de pointeur ou de référence au début du nom de la fonction comme indiqué ci-dessous.  Les parenthèses, normalement facultatives, sont requises pour distinguer un pointeur désignant une fonction d'une fonction qui retourne un pointeur :  
  
```  
int (*pf)(int); // pointer to function returning int  
int *f(int i); // function returning pointer to int  
int (&pf)(int); // reference to function   
```  
  
 Les pointeurs désignant des fonctions membres se distinguent par des spécificateurs de noms imbriqués :  
  
```  
int (X::* pmf)(); // pointer to member function of X returning int  
int* (X::* pmf)(); // pointer to member function returning pointer to int  
```  
  
 Voir aussi [des pointeurs vers membres](../cpp/pointers-to-members.md).  
  
 **Fonctions et objets dans la même déclaration**  
  
 Des fonctions et des objets peuvent être déclarés dans une même déclaration, comme suit :  
  
```  
int i, *j, f(int k);  // int, pointer to int, function returning int  
```  
  
 La syntaxe peut être équivoque dans certaines circonstances.  La déclaration suivante  
  
```  
int* i, f(int k);  // pointer to int, function returning int (not int*)  
```  
  
 peut ressembler à la déclaration d'un pointeur `int` et d'une fonction retournant `int*`, mais il n'en est rien.  En effet, * fait partie du déclarateur pour `i` et non pas du déclarateur pour `f`.  
  
 **Simplification de la syntaxe des déclarateurs avec typedef**  
  
 Une meilleure technique, toutefois, consiste à utiliser `typedef` ou une combinaison de parenthèses et du mot clé `typedef`. Déclarez un tableau de pointeurs désignant des fonctions :  
  
```  
//  Function returning type int that takes one   
//   argument of type char *.  
typedef int (*PIFN)( char * );  
//  Declare an array of 7 pointers to functions   
//   returning int and taking one argument of type   
//   char *.  
PIFN pifnDispatchArray[7];  
```  
  
 La déclaration équivalente peut être écrite sans la déclaration `typedef`, mais cela s'avère si complexe que le risque d'erreurs dépasse les avantages :  
  
```  
int ( *pifnDispatchArray[7] )( char * );  
```  
  
 Pour plus d’informations sur typedef, consultez [alias et typedefs](aliases-and-typedefs-cpp.md).  
  
 Des pointeurs, des références et des tableaux d'un même type de base peuvent être associés dans une déclaration unique (séparés par des virgules) comme suit :  
  
```  
int a, *b, c[5], **d, &e=a;  
```  
  
 **Syntaxe des déclarateurs plus complexe**  
  
-   Des déclarateurs de pointeurs, références, tableaux et fonctions peuvent être associés pour spécifier des objets tels que des tableaux de pointeurs désignant des fonctions, des pointeurs désignant des tableaux, etc.  
  
-   La syntaxe récursive suivante décrit pleinement la syntaxe des déclarateurs de pointeurs.  
  
-   Un `declarator` est défini en tant que l'un des éléments suivants :  
  
```  
1. identifier   
2. qualified-name   
3. declarator ( argument-list ) [cv-qualfiers] [exception-spec]  
4. declarator [ [ constant-expression ] ]   
  
5. pointer-operatordeclarator   
6. ( declarator )  
```  
  
-   et *opérateur de pointeur* est un des :  
  
```  
  
      * [cv-qualifiers]  
& [cv-qualifiers]  
::nested-name-specifier * [cv-qualfiers]  
```  
  
 Comme un déclarateur peut contenir des déclarateurs, il est possible de construire des types dérivés plus complexes, tels que des tableaux de pointeurs ou des fonctions retournant des tableaux de pointeurs de fonction, à l'aide des règles ci-dessus.  Pour former chaque étape de la construction, commencez avec l'identificateur représentant le type de données de base et appliquez la règle de syntaxe ci-dessus avec l'expression précédente comme `declarator`.  L'ordre dans lequel vous appliquez les règles de syntaxe doit être inverse à l'ordre dans lequel l'expression est énoncée en anglais.  Si vous appliquez le *opérateur de pointeur* règle de syntaxe pour une expression de tableau ou de fonction, utilisez des parenthèses si vous souhaitez un pointeur vers le tableau ou la fonction, comme la dernière ligne dans le tableau ci-dessous.  
  
 L'exemple suivant illustre la construction de « pointeur désignant un tableau de 10 pointeurs désignant des valeurs int ».  
  
|Expression verbale|Déclarateur|Règle de syntaxe appliquée|  
|-----------------------|----------------|-------------------------|  
||`i`|1|  
|pointeur(s) désignant|`*i`|5|  
|tableau de 10|`(*i)[10]`|4|  
|pointeur désignant|`*((*i)[10])`|6 puis 5|  
  
 Lorsque plusieurs modificateurs de pointeur, référence, tableau ou fonction sont utilisés, les déclarateurs peuvent devenir relativement complexes.  La rubrique [interprétation de déclarateurs plus complexes](../c-language/interpreting-more-complex-declarators.md) explique comment lire la syntaxe des déclarateurs plus complexe.  La rubrique s’applique à C et C++, même si en C++, partout où le * est utilisé pour indiquer un pointeur, un nom qualifié tel que MyClass ::\* peut être utilisé pour spécifier un pointeur vers un membre d’une classe.
