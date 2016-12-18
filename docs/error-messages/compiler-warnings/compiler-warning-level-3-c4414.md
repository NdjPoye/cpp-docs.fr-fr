---
title: "Avertissement du compilateur (niveau 3) C4414 | Microsoft Docs"
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
  - "C4414"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4414"
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4414
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : saut de type short vers la fonction converti en near  
  
 Des sauts courts génèrent une instruction compacte qui crée une branche vers une adresse dans une plage limitée à partir de l'instruction.  L'instruction inclut un court offset qui représente la distance entre le saut et l'adresse cible, la définition de la fonction.  Pendant la liaison, une fonction peut être déplacée ou soumise à des optimisations de temps de liaison entraînant le passage de la fonction en dehors de la plage accessible à partir d'un court offset.  Le compilateur doit générer un enregistrement spécial pour le saut, qui requiert une instruction jump NEAR ou FAR.  Le compilateur a effectué la conversion.  
  
 Par exemple, le code suivant génère l'erreur C4414 :  
  
```  
// C4414.cpp  
// compile with: /W3 /c  
// processor: x86  
int DoParityEven();  
int DoParityOdd();  
unsigned char global;  
int __declspec(naked) DoParityEither()  
{  
   __asm  
   {  
      test global,0  
      jpe SHORT DoParityEven  // C4414  
      jmp SHORT DoParityOdd   // C4414  
   }  
}  
```