---
title: "Op&#233;rateur de bits OR exclusif&#160;: ^ | Microsoft Docs"
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
  - "^ (opérateur)"
  - "opérateurs de bits, OR (opérateur)"
  - "opérateur OR exclusif"
  - "opérateurs (C++), au niveau du bit"
  - "opérateurs (C++), logique"
  - "OR (opérateur), exclusif au niveau du bit"
  - "XOR (opérateur)"
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateur de bits OR exclusif&#160;: ^
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
expression ^ expression  
```  
  
## Notes  
 L'opérateur de bits OR exclusif \(**^**\) compare chaque bit de son premier opérande au bit correspondant de son second opérande.  Si un bit est 0 et que l'autre bit est 1, le bit de résultat correspondant prend la valeur 1.  Sinon, le bit de résultat correspondant a la valeur 0.  
  
 Les deux opérandes de l'opérateur de bits OR exclusif doivent être de types intégraux.  Les conversions arithmétiques courantes traitées dans [Conversions arithmétiques](../misc/arithmetic-conversions.md) s'appliquent aux opérandes.  
  
## Mot clé d'opérateur pour ^  
 L'opérateur **xor** est l'équivalent textuel de **^**.  Il existe deux moyens d'accéder à l'opérateur **xor** dans vos programmes : inclure le fichier d'en\-tête `iso646.h` ou compiler avec l'option du compilateur [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(désactivation des extensions de langage\).  
  
## Exemple  
  
```  
// expre_Bitwise_Exclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise exclusive OR  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xFFFF;      // pattern 1111 ...  
  
   cout  << hex << ( a ^ b ) << endl;   // prints "aaaa" pattern 1010 ...  
}  
```  
  
## Voir aussi  
 [Opérateurs de bits C\+\+](../misc/cpp-bitwise-operators.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs de bits C](../c-language/c-bitwise-operators.md)