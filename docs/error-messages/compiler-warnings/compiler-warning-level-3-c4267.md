---
title: "Avertissement du compilateur (niveau 3) C4267 | Microsoft Docs"
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
  - "C4267"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4267"
ms.assetid: 2fa2f13f-fa4f-47bb-ad8f-6cb19cfc91e6
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4267
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : conversion de 'size\_t' en 'type', perte possible de données  
  
 Le compilateur a détecté une conversion de `size_t` en un type plus petit.  
  
 Pour résoudre cet avertissement, utilisez `size_t` à la place de `type`.  Vous pouvez également utiliser un type intégral au moins aussi grand que `size_t`.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4267.  
  
```  
// C4267.cpp  
// compile by using: cl /W4 C4267.cpp  
void Func1(short) {}  
void Func2(int) {}  
void Func3(long) {}  
void Func4(size_t) {}  
  
int main() {  
   size_t bufferSize = 10;  
   Func1(bufferSize);   // C4267 for all platforms  
   Func2(bufferSize);   // C4267 only for 64-bit platforms  
   Func3(bufferSize);   // C4267 only for 64-bit platforms  
   Func4(bufferSize);   // OK for all platforms  
}  
```