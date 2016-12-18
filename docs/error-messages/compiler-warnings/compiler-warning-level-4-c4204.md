---
title: "Avertissement du compilateur (niveau 4) C4204 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4204"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4204"
ms.assetid: 298d2880-6737-448e-b711-15572d540200
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4204
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : initialiseur d'agrégat non constant  
  
 Avec les extensions Microsoft \(\/Ze\), vous pouvez initialiser des types d'agrégats \(tableaux, structures, unions et classes\) avec des valeurs qui ne sont pas des constantes.  
  
## Exemple  
  
```  
// C4204.c  
// compile with: /W4  
int func1()  
{  
   return 0;  
}  
struct S1  
{  
   int i;  
};  
  
int main()  
{  
   struct S1 s1 = { func1() };   // C4204  
   return s1.i;  
}  
```  
  
 De telles initialisations sont non valides sous compatibilité ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).