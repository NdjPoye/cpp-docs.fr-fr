---
title: "null, instruction | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "expressions (C++), null"
  - "instruction null"
  - "valeurs null, expressions"
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# null, instruction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'instruction null est une instruction d'expression dans laquelle l'*expression* est manquante.  Elle s'avère utile lorsque la syntaxe du langage demande une instruction, mais pas d'évaluation d'expression.  Elle se compose d'un point\-virgule.  
  
 Les instructions null sont couramment utilisées comme espaces réservés dans les instructions d'itération ou comme instructions sur lesquelles placer des étiquettes à la fin d'instructions composées ou de fonctions.  
  
 Le fragment de code suivant montre comment copier une chaîne vers une autre et comporte l'instruction null :  
  
```  
// null_statement.cpp  
char *myStrCpy( char *Dest, const char *Source )  
{  
    char *DestStart = Dest;  
  
    // Assign value pointed to by Source to  
    // Dest until the end-of-string 0 is  
    // encountered.  
    while( *Dest++ = *Source++ )  
        ;   // Null statement.  
  
    return DestStart;  
}  
  
int main()  
{  
}  
```  
  
## Voir aussi  
 [Instruction d'expression](../cpp/expression-statement.md)