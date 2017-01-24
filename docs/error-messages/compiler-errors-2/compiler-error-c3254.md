---
title: "Erreur du compilateur C3254 | Microsoft Docs"
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
  - "C3254"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3254"
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3254
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'substitution explicite' : la classe contient une substitution explicite 'substitution', mais ne dérive pas d'une interface qui contient la déclaration de fonction  
  
 Lorsque vous [substituez explicitement](../../cpp/explicit-overrides-cpp.md) une méthode, la classe qui contient la substitution doit provenir directement ou indirectement du type qui contient la fonction que vous substituez.  
  
 L'exemple suivant génère l'erreur C3254 :  
  
```  
// C3254.cpp  
__interface I  
{  
   void f();  
};  
  
__interface I1 : I  
{  
};  
  
struct A /* : I1 */  
{  
   void I1::f()  
   {   // C3254, uncomment : I1 to resolve this C3254  
   }  
};  
  
int main()  
{  
}  
```