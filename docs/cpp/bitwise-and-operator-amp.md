---
title: "Op&#233;rateur de bits AND&#160;: &amp; | Microsoft Docs"
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
  - "bitand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& (opérateur), opérateurs de bits"
  - "AND (opérateur)"
  - "opérateurs de bits, AND (opérateur)"
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateur de bits AND&#160;: &amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
expression   
&  
 expression  
  
```  
  
## Notes  
 Les expressions peuvent être d'autres expressions\-et, ou \(en fonction des restrictions de type indiquées ci\-dessous\) des expressions d'égalité, des expressions relationnelles, des expressions additives, des expressions multiplicatives, des expressions de pointeur vers membre, des expressions de casts, des expressions unaires, des expressions suffixées ou des expressions primaires.  
  
 L'opérateur de bits AND \(**&**\) compare chaque bit du premier opérande au bit correspondant du second opérande.  Si les deux bits sont 1, le bit de résultat correspondant a la valeur 1.  Sinon, le bit de résultat correspondant a la valeur 0.  
  
 Les deux opérandes de l'opérateur de bits AND doivent être de types intégraux.  Les conversions arithmétiques habituelles traitées dans [Conversions arithmétiques](../misc/arithmetic-conversions.md) s'appliquent aux opérandes.  
  
## Mot clé Operator pour &  
 L'opérateur `bitand` est l'équivalent textuel de **&**.  Il existe deux moyens d'accéder à l'opérateur `bitand` dans vos programmes : incluez le fichier d'en\-tête `iso646.h` ou compilez avec l'option de compilateur [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(Désactivation des extensions de langage\).  
  
## Exemple  
  
```  
// expre_Bitwise_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise AND  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0xFFFF;      // pattern 1111 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a & b ) << endl;   // prints "aaaa", pattern 1010 ...  
}  
```  
  
## Voir aussi  
 [Opérateurs de bits C\+\+](../misc/cpp-bitwise-operators.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs de bits C](../c-language/c-bitwise-operators.md)