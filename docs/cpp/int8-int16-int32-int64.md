---
title: "__int8, __int16, __int32, __int64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__int8_cpp"
  - "__int64"
  - "__int8"
  - "__int16"
  - "__int16_cpp"
  - "__int64_cpp"
  - "__int32_cpp"
  - "__int32"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__int16 (mot clé) (C++)"
  - "__int32 (mot clé) (C++)"
  - "__int64 (mot clé) (C++)"
  - "__int8 (mot clé) (C++)"
  - "integer (type de données), types d'entier en C++"
  - "types d'entier (C++)"
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# __int8, __int16, __int32, __int64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Prise en charge des fonctionnalités Microsoft C\/C\+\+ pour les types d'entiers dimensionnés.  Vous pouvez déclarer des variables de type entier à 8, 16, 32 ou 64 bits à l'aide du spécificateur de type **\_\_int***n*, où *n* est égal à 8, 16, 32 ou 64.  
  
 L'exemple suivant déclare une variable pour chacun de ces types d'entiers dimensionnés :  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 Les types `__int8`, `__int16` et `__int32` sont des synonymes des types ANSI de la même taille, et permettent d'écrire du code portable qui se comporte de façon identique sur plusieurs plateformes.  Le type de données `__int8` est synonyme du type `char`, `__int16` est synonyme du type **short** et `__int32` est synonyme du type `int`.  Le type `__int64` n'a aucun équivalent ANSI.  
  
## Exemple  
 L'exemple suivant indique qu'un paramètre \_\_int*xx* sera promu en `int` :  
  
```  
// sized_int_types.cpp  
  
#include <stdio.h>  
  
void func(int i) {  
    printf_s("%s\n", __FUNCTION__);  
}  
  
int main()  
{  
    __int8 i8 = 100;  
    func(i8);   // no void func(__int8 i8) function  
                // __int8 will be promoted to int  
}  
```  
  
  **func**   
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Types fondamentaux](../cpp/fundamental-types-cpp.md)   
 [Plages de types de données](../cpp/data-type-ranges.md)