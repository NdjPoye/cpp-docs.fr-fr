---
title: "Expressions primaires | Microsoft Docs"
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
  - "expressions (C++), de littéral"
  - "expressions (C++), nom"
  - "expressions (C++), principal"
  - "expressions (C++), noms qualifiés"
  - "expressions primaires"
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Expressions primaires
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les expressions primaires sont des blocs de construction d'expressions plus complexes.  Il s'agit de littéraux, de noms et de noms qualifiés par l'opérateur résolution\-portée \(`::`\).  Une expression primaire peut prendre chacune des formes suivantes :  
  
```  
  
        literal  
this  
:: name  
name   
( expression )  
```  
  
 Un *literal* est une expression primaire constante.  Son type dépend de la forme de sa spécification.  Consultez [Littéraux](../cpp/numeric-boolean-and-pointer-literals-cpp.md) pour des informations complètes sur la spécification des littéraux.  
  
 Le mot clé **this** est un pointeur vers un objet de classe.  Il est disponible dans les fonctions membres non statiques et pointe vers l'instance de la classe pour laquelle la fonction est appelée.  Le mot clé **this** ne peut pas être utilisé en dehors du corps d'une fonction membre de classe.  
  
 Le type du pointeur **this** est **\*const** `type` \(où `type` est le nom de classe\) dans les fonctions qui ne modifient pas spécifiquement le pointeur **this**.  L'exemple suivant montre des déclarations de fonctions membres et les types **this** :  
  
```  
// expre_Primary_Expressions.cpp  
// compile with: /LD  
class Example  
{  
public:  
    void Func();          //  * const this  
    void Func() const;    //  const * const this  
    void Func() volatile; //  volatile * const this  
};  
```  
  
 Consultez [Type de ce pointeur](../misc/type-of-this-pointer.md) pour plus d'informations sur la modification du type du pointeur **this**.  
  
 L'opérateur résolution\-portée \(`::`\) suivi d'un nom constitue une expression primaire.  Ces noms doivent être des noms au niveau de la portée globale, pas des noms de membres.  Le type de cette expression est déterminé par la déclaration du nom.  Il s'agit d'une l\-value \(autrement dit, il peut apparaître dans la partie gauche d'une expression opérateur d'assignation\) si le nom de déclaration est une l\-value.  L'opérateur résolution\-portée permet de faire référence à un nom global, même si ce nom est masqué dans la portée actuelle.  Consultez [Portée](../cpp/scope-visual-cpp.md) pour obtenir un exemple d'utilisation de l'opérateur de résolution de portée.  
  
 Une expression placée entre parenthèses est une expression principale dont le type et la valeur sont identiques à ceux de l'expression qui n'est pas entre parenthèses.  Il s'agit d'une l\-value si l'expression qui n'est pas entre parenthèses est une l\-value.  
  
 Dans le contexte de la syntaxe d'expression primaire indiquée ci\-dessus, *name* signifie tout élément dans la syntaxe décrite pour [Noms](http://msdn.microsoft.com/fr-fr/1c49cc24-08d5-4884-b170-ba8ed42d80db), bien que lors de l'utilisation de l'opérateur de résolution de portée avant le nom, les types de noms qui peuvent uniquement se produire dans une classe ne sont pas autorisés.  Cela inclut les noms de fonctions de conversion définies par l'utilisateur, et les noms de destructeur.  
  
 Les exemples d'expressions principaux incluent :  
  
```  
100 // literal  
'c' // literal  
this // in a member function, a pointer to the class instance  
::func // a global function  
::operator + // a global operator function  
::A::B // a global qualified name  
( i + 1 ) // a parenthesized expression  
```  
  
 Les exemples suivants sont tous considérés comme des *names* et par conséquent des expressions primaires, de différentes formes :  
  
```  
MyClass // a identifier  
MyClass::f // a qualified name  
operator = // an operator function name  
operator char* // a conversion operator function name  
~MyClass // a destructor name  
A::B   // a qualified name  
A<int> // a template id  
```  
  
## Voir aussi  
 [Types d'expressions](../cpp/types-of-expressions.md)