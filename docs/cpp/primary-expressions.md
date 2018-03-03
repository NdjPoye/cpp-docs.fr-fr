---
title: Expressions primaires | Documents Microsoft
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
- primary expressions
- expressions [C++], name
- expressions [C++], literal
- expressions [C++], primary
- expressions [C++], qualified names
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0a6e811e1fe074ce488b09fca29926989bc7f355
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="primary-expressions"></a>Expressions primaires
Les expressions primaires sont des blocs de construction d'expressions plus complexes. Il s'agit de littéraux, de noms et de noms qualifiés par l'opérateur résolution-portée (`::`).  Une expression primaire peut prendre chacune des formes suivantes :  
  
```  
  
      literal  
      this  
:: namename( expression )  
```  
  
 A *littéral* est une expression primaire constante. Son type dépend de la forme de sa spécification. Consultez [littéraux](../cpp/numeric-boolean-and-pointer-literals-cpp.md) pour plus d’informations sur la spécification des littéraux.  
  
 Le **cela** (mot clé) est un pointeur vers un objet de classe. Il est disponible dans les fonctions membres non statiques et pointe vers l'instance de la classe pour laquelle la fonction est appelée. Le **cela** mot clé ne peut pas être utilisé en dehors du corps d’une fonction membre de classe.  
  
 Le type de la **cela** pointeur est `type`  **\*const** (où `type` est le nom de classe) dans les fonctions de modification ne sont pas spécifiquement le **cette** pointeur. L’exemple suivant affiche des membres, déclarations de fonction et les types de **cela**:  
  
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
  
 Consultez [ce pointeur](this-pointer.md) pour plus d’informations sur la modification du type de la **cela** pointeur.  
  
 L'opérateur résolution-portée (`::`) suivi d'un nom constitue une expression primaire.  Ces noms doivent être des noms au niveau de la portée globale, pas des noms de membres.  Le type de cette expression est déterminé par la déclaration du nom. Il s'agit d'une l-value (autrement dit, il peut apparaître dans la partie gauche d'une expression opérateur d'assignation) si le nom de déclaration est une l-value. L’opérateur résolution-portée permet de faire référence à un nom global, même si ce nom est masqué dans la portée actuelle. Consultez [étendue](../cpp/scope-visual-cpp.md) pour obtenir un exemple montrant comment utiliser l’opérateur de résolution de portée.  
  
 Une expression placée entre parenthèses est une expression principale dont le type et la valeur sont identiques à ceux de l'expression qui n'est pas entre parenthèses. Il s'agit d'une l-value si l'expression qui n'est pas entre parenthèses est une l-value.  
  
 Dans le contexte de la syntaxe d’expression primaire ci-dessus, *nom* signifie que n’importe où dans la syntaxe décrite pour [noms](http://msdn.microsoft.com/en-us/1c49cc24-08d5-4884-b170-ba8ed42d80db), bien que lorsque à l’aide de l’opérateur de résolution de portée avant le nom, les types de noms qui peut se produire uniquement dans une classe ne sont pas autorisés.  Cela inclut les noms de fonctions de conversion définies par l'utilisateur, et les noms de destructeur.  
  
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
  
 Les exemples ci-dessous sont tous considérés comme *noms*et des expressions primaires par conséquent, dans différentes formes :  
  
```  
MyClass // a identifier  
MyClass::f // a qualified name  
operator = // an operator function name  
operator char* // a conversion operator function name  
~MyClass // a destructor name  
A::B   // a qualified name  
A<int> // a template id  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Types d’expressions](../cpp/types-of-expressions.md)