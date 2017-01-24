---
title: "Op&#233;rateurs d&#39;acc&#232;s aux membres&#160;: . et -&gt; | Microsoft Docs"
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
  - "."
  - "->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ". d'opérateur"
  - "-> (opérateur)"
  - "opérateur point (.)"
  - "accès aux membres"
  - "accès aux membres, expressions"
  - "accès aux membres, opérateurs"
  - "opérateurs (C++), accès aux membres"
  - "opérateurs suffixés"
ms.assetid: f8fc3df9-d728-40c5-b384-276927f5f1b3
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs d&#39;acc&#232;s aux membres&#160;: . et -&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
      postfix-expression   
      . name  
postfix-expression –> name  
```  
  
## Notes  
 Les opérateurs d'accès aux membres **.** et **\-\>** sont utilisés pour faire référence aux membres de structures, d'unions et de classes.  Les expressions d'accès aux membres ont la valeur et le type du membre sélectionné.  
  
 Il existe deux formes d'expressions d'accès aux membres :  
  
1.  Dans la première forme, *postfix\-expression* représente une valeur de type struct, classe ou union et *name* désigne un membre de la structure, union ou classe spécifiée.  La valeur de l'opération est celle de *name* ; il s'agit d'une l\-value si *postfix\-expression* est une l\-value.  
  
2.  Dans la seconde forme, *postfix\-expression* représente un pointeur vers une structure, union ou classe et *name* désigne un membre de la structure, union ou classe spécifiée.  La valeur est celle de *name* ; il s'agit d'une l\-value.  L'opérateur **–\>** déréférence le pointeur.  Par conséquent, les expressions *e***–\>**`member` et **\(\****e***\)**.`member` \(où *e* représente un pointeur\) génèrent des résultats équivalents \(sauf lorsque les opérateurs **–\>** ou **\*** sont surchargés\).  
  
## Exemple  
 L'exemple suivant illustre les deux formes de l'opérateur d'accès aux membres.  
  
```  
// expre_Selection_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Date {  
   Date(int i, int j, int k) : day(i), month(j), year(k){}  
   int month;  
   int day;  
   int year;  
};  
  
int main() {  
   Date mydate(1,1,1900);  
   mydate.month = 2;     
   cout  << mydate.month << "/" << mydate.day  
         << "/" << mydate.year << endl;  
  
   Date *mydate2 = new Date(1,1,2000);  
   mydate2->month = 2;  
   cout  << mydate2->month << "/" << mydate2->day  
         << "/" << mydate2->year << endl;  
   delete mydate2;  
}  
```  
  
  **2\/1\/1900**  
**2\/1\/2000**   
## Voir aussi  
 [Expressions suffixées](../cpp/postfix-expressions.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Classes et structs](../cpp/classes-and-structs-cpp.md)   
 [Structure et membres d'union](../c-language/structure-and-union-members.md)