---
title: "Op&#233;rateur de compl&#233;ment &#224; 1&#160;: ~ | Microsoft Docs"
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
  - "~"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~ (opérateur), syntaxe"
  - "opérateur de complément de bits"
  - "compl (opérateur)"
  - "opérateur de complément à 1"
  - "opérateur de complément à 1 (~)"
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateur de compl&#233;ment &#224; 1&#160;: ~
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
~ cast-expression  
```  
  
## Notes  
 L'opérateur de complément à un \(`~`\), parfois appelé l'opérateur de complément de bits, génère un complément à un au niveau du bit de son opérande.  Autrement dit, chaque bit qui est 1 dans l'opérande est 0 dans le résultat.  Inversement, chaque bit qui est 0 dans l'opérande est 1 dans le résultat.  L'opérande de l'opérateur de complément à un doit être un type intégral.  
  
## Mot clé Operator pour ~  
 L'opérateur `compl` est l'équivalent textuel de `~`.  Il existe deux moyens d'accéder à l'opérateur `compl` dans vos programmes : incluez le fichier d'en\-tête `iso646.h` ou compilez avec [\/Za](../build/reference/za-ze-disable-language-extensions.md).  
  
## Exemple  
  
```  
// expre_One_Complement_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main () {  
   unsigned short y = 0xFFFF;  
   cout << hex << y << endl;  
   y = ~y;   // Take one's complement  
   cout << hex << y << endl;  
}  
```  
  
 Dans cet exemple, la nouvelle valeur assignée à `y` est le complément à 1 de la valeur non signée 0xFFFF ou 0x0000.  
  
 La promotion intégrale est exécutée sur les opérandes intégraux et le type résultant est le type vers lequel l'opérande est promu.  Pour plus d'informations sur la façon dont la promotion est effectuée, consultez [Promotions intégrales](../misc/integral-promotions.md).  
  
## Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs arithmétiques unaires](../c-language/unary-arithmetic-operators.md)