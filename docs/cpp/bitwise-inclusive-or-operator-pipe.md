---
title: "Op&#233;rateur de bits OR inclusif&#160;: | | Microsoft Docs"
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
  - "bitor"
  - "|"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "| (opérateur)"
  - "opérateurs de bits, OR (opérateur)"
  - "OR (opérateur inclusif)"
  - "OR (opérateur), inclusif au niveau du bit"
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateur de bits OR inclusif&#160;: |
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
expression   
|  
 expression  
  
```  
  
## Notes  
 Opérateur OR inclusif de bits \(         **&#124;** \) compare chaque bit de son premier opérande au bit correspondant de son second opérande.  Si l'un des bits est 1, le bit correspondant de résultat a la valeur 1.  Sinon, le bit de résultat correspondant a la valeur 0.  
  
 Les deux opérandes de l'opérateur OR inclusif de bits doivent être de types intégraux.  Les conversions arithmétiques courantes traitées dans [Conversions arithmétiques](../misc/arithmetic-conversions.md) s'appliquent aux opérandes.  
  
## Mot clé Operator pour &#124;  
 L'opérateur `bitor` est l'équivalent textuel de              **&#124;** .  Il existe deux moyens d'accéder à l'opérateur `bitor` dans vos programmes : incluez le fichier d'en\-tête `iso646.h` ou compilez avec l'option de compilateur [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(Désactivation des extensions de langage\).  
  
## Exemple  
  
```  
// expre_Bitwise_Inclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise inclusive OR  
#include <iostream>  
using namespace std;  
  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...  
}  
```  
  
## Voir aussi  
 [Opérateurs de bits C\+\+](../misc/cpp-bitwise-operators.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs de bits C](../c-language/c-bitwise-operators.md)