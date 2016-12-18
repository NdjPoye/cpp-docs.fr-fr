---
title: "Avertissement du compilateur (niveau 4) C4032 | Microsoft Docs"
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
  - "C4032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4032"
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le paramètre formel 'numéro' a un type différent lors de sa promotion  
  
 Le type de paramètre n'est pas compatible, par des promotions par défaut, avec le type d'une déclaration précédente.  
  
 C'est une erreur en C ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\), mais un avertissement avec les extensions Microsoft \(\/Ze\).  
  
## Exemple  
  
```  
// C4032.c  
// compile with: /W4  
void func();  
void func(char);   // C4032, char promotes to int  
  
int main()  
{  
}  
```