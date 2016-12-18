---
title: "Avertissement du compilateur (niveau 2) C4756 | Microsoft Docs"
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
  - "C4756"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4756"
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 2) C4756
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

débordement d'une constante arithmétique  
  
 Le compilateur a généré une exception en faisant une constante arithmétique pendant la compilation.  
  
 L'exemple suivant génère l'erreur C4756 :  
  
```  
// C4756.cpp  
// compile with: /W2 /Od  
int main()  
{  
   float f = 1e100+1e100;   // C4756  
}  
```