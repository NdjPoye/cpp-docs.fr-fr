---
title: "Erreur du compilateur C2090 | Microsoft Docs"
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
  - "C2090"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2090"
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2090
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

tableau retourné par la fonction  
  
 Une fonction ne peut pas retourner un tableau.  Retournez plutôt un pointeur vers un tableau.  
  
 L'exemple suivant génère l'erreur C2090 :  
  
```  
// C2090.cpp  
int func1(void)[] {}   // C2090  
```  
  
 Résolution possible :  
  
```  
// C2090b.cpp  
// compile with: /c  
int* func2(int * i) {  
   return i;  
}  
```