---
title: "Erreur du compilateur C2703 | Microsoft Docs"
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
  - "C2703"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2703"
ms.assetid: 384295c3-643d-47ae-a9a6-865b3036aa84
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2703
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

instruction \_\_leave non conforme  
  
 Une instruction `__leave` doit se trouver dans un bloc `__try`.  
  
 L'exemple suivant génère l'erreur C2703 :  
  
```  
// C2703.cpp  
int main() {  
   __leave;   // C2703  
   __try {  
      // try the following line instead  
      __leave;  
   }  
   __finally {}  
}  
```