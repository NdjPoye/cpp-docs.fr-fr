---
title: "Op&#233;rateur d’indice&#160;: | Microsoft Docs"
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
  - "[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opérateurs (C++), indice"
  - "opérateurs suffixés"
  - "[] (opérateur)"
  - "opérateur d’indice, syntaxe"
ms.assetid: 69c31494-52da-4dd0-8bbe-6ccbfd50f197
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateur d’indice&#160;:
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
postfix-expression [ expression ]  
```  
  
## Notes  
 Une expression suffixée \(qui peut également être une expression primaire\) suivie de l'opérateur Indice, **\[ \]**, spécifie l'indexation de tableau.  
  
 Pour plus d'informations sur les tableaux managés, consultez [Arrays](../windows/arrays-cpp-component-extensions.md).  
  
 Généralement, la valeur représentée par *postfix\-expression* est une valeur de pointeur, par exemple un identificateur de tableau, et *expression* est une valeur intégrale \(y compris les types énumérés\).  Toutefois, sur le plan de la syntaxe, il est requis que l'une des expressions soit de type pointeur et l'autre de type intégral.  La valeur intégrale peut donc se trouver dans la position *postfix\-expression* et la valeur de pointeur peut être entre crochets, dans la position *expression* ou d'indice.  Prenons le fragment de code suivant :  
  
```  
int nArray[5] = { 0, 1, 2, 3, 4 };  
cout << nArray[2] << endl;            // prints "2"  
cout << 2[nArray] << endl;            // prints "2"  
```  
  
 Dans l'exemple précédent, l'expression `nArray[2]` est identique à `2[nArray]`.  Cela est dû au fait que le résultat d'une expression d'indice *e1***\[** *e2* **\]** est donné par :  
  
 **\*\( \(** *e2* **\)** *\+* **\(***e1***\) \)**  
  
 L'adresse transmise par l'expression n'est pas *e2* octets à partir de l'adresse *e1*.  En revanche, l'adresse est mise à l'échelle pour transmettre l'objet suivant du tableau *e2*.  Exemple :  
  
```  
double aDbl[2];  
```  
  
 Les adresses de `aDb[0]` et `aDb[1]` ont 8 octets de différence. Il s'agit de la taille d'un objet de type **double**.  Cette mise à l'échelle selon le type d'objet est effectuée automatiquement par le langage C\+\+ et est définie dans [Opérateurs additifs](../cpp/additive-operators-plus-and.md), où l'ajout et la soustraction des opérandes de type pointeur sont abordés.  
  
 Une expression d'indice peut également avoir plusieurs indices, comme suit :  
  
 *expression1* **\[***expression2***\] \[***expression3***\]**...  
  
 Les expressions d'indice s'associent de gauche à droite.  L'expression d'indice extrême gauche, *expression1***\[***expression2***\]**, est évaluée en premier.  L'adresse qui résulte de l'ajout d'*expression1* et *expression2* forme une expression de pointeur. Ensuite, *expression3* est ajouté à cette expression de pointeur pour former une nouvelle expression de pointeur, et ainsi de suite jusqu'à ce que la dernière expression d'indice ait été ajoutée.  L'opérateur d'indirection \(**\***\) est appliqué après l'évaluation de la dernière expression d'indice, à moins que la valeur de pointeur finale traite un type tableau.  
  
 Les expressions à indices multiples font référence à des éléments de tableaux multidimensionnels.  Un tableau multidimensionnel est un tableau dont les éléments sont des tableaux.  Par exemple, le premier élément d'un tableau tridimensionnel est un tableau à deux dimensions.  L'exemple suivant déclare et initialise un tableau de caractères simple à deux dimensions :  
  
```  
// expre_Subscript_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
#define MAX_ROWS 2  
#define MAX_COLS 2  
  
int main() {  
   char c[ MAX_ROWS ][ MAX_COLS ] = { { 'a', 'b' }, { 'c', 'd' } };  
   for ( int i = 0; i < MAX_ROWS; i++ )  
      for ( int j = 0; j < MAX_COLS; j++ )  
         cout << c[ i ][ j ] << endl;  
}  
```  
  
## Indices positifs et négatifs  
 Le premier élément d'un tableau est l'élément 0.  La plage d'un tableau C\+\+ est comprise entre *array*\[0\] et *array*\[*size* – 1\].  Toutefois, C\+\+ prend en charge les indices positifs et négatifs.  Les indices négatifs doivent rester dans les limites du tableau. Sinon, les résultats sont imprévisibles.  Le code suivant montre des indices de tableau positifs et négatifs :  
  
```  
#include <iostream>  
using namespace std;  
  
int main() {  
    int intArray[1024];  
    for (int i = 0, j = 0; i < 1024; i++)  
    {  
        intArray[i] = j++;  
    }  
  
    cout << intArray[512] << endl;// 512  
  
    int *midArray = &intArray[512];  // pointer to the middle of the array  
  
    cout << midArray[-256] << endl;   // 256  
  
    cout << intArray[-256] << endl; // unpredictable  
}  
```  
  
 L'indice négatif de la ligne lasta peut provoquer une erreur d'exécution, car il produit une adresse 256 octets plus bas en mémoire que l'origine du tableau.  Le pointeur `midArray` est initialisé au milieu de `intArray`. Il est donc possible d'utiliser à la fois des index de tableau négatifs et positifs sur ce dernier.  Les erreurs d'indice de tableau ne génèrent pas d'erreurs de compilation, mais ils produisent des résultats imprévisibles.  
  
 L'opérateur d'indice est commutatif.  Par conséquent, les expressions *array*\[*index*\] et *array*\[*array*\] sont obligatoirement équivalentes, à condition que l'opérateur d'indice ne soit pas surchargé \(voir [Opérateurs surchargés](../cpp/operator-overloading.md)\).  La première forme constitue la pratique de codage la plus courante, mais les deux fonctionnent.  
  
## Voir aussi  
 [Expressions suffixées](../cpp/postfix-expressions.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Tableaux](../cpp/arrays-cpp.md)   
 [Tableaux unidimensionnels](../c-language/one-dimensional-arrays.md)   
 [Tableaux multidimensionnels](../c-language/multidimensional-arrays-c.md)