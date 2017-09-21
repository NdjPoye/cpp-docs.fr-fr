---
title: "Avertissement du compilateur (niveau 4) C4202 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4202"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4202"
ms.assetid: 253293aa-97a3-4878-a2e8-c6cc9e20b1cb
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 4) C4202
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : '...' : paramètre de prototype dans la liste de noms non conforme  
  
 Une définition de fonction de style ancien contient des arguments variables.  Ces définitions génèrent une erreur sous compatibilité ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).  
  
## Exemple  
  
```  
// C4202.c  
// compile with: /W4  
void func( a, b, ...)   // C4202  
int a, b;  
{}  
  
int main()  
{  
}  
```