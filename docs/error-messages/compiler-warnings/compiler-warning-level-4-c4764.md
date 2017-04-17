---
title: "Avertissement du compilateur (niveau&#160;4) C4764 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4764"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4764"
ms.assetid: 7bd4296f-966b-484c-bf73-8dbc8e85b4a9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avertissement du compilateur (niveau&#160;4) C4764
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Impossible d'aligner les objets de bloc catch sur plus de 16 octets  
  
 Un alignement supérieur à 16 a été spécifié. Toutefois, sur certaines plates\-formes, si la fonction lève une exception, la pile force un alignement qui n’est pas supérieur à 16.  
  
## Exemple  
 L’exemple suivant génère l’avertissement C4764 :  
  
```  
// C4764.cpp // compile with: /W4 /EHsc // processor: x64 IPF #include <stdio.h> class A { public: int x; }; typedef __declspec(align(32)) A ALIGNEDA; int main() { ALIGNEDA a; try { a.x = 15; throw a; } catch (ALIGNEDA b) // can’t align b to > 16 bytes { printf_s("%d\n", b.x); } }   // C4764  
```