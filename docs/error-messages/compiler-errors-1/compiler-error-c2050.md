---
title: "Erreur du compilateur C2050 | Microsoft Docs"
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
  - "C2050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2050"
ms.assetid: 66aaed7d-00db-4ce1-a9d6-4447c1cf07ce
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

expression de switch non intégrale  
  
 L'expression de `switch` correspond à une valeur non entière.  Pour corriger l'erreur, n'utilisez que des valeurs entières dans des instructions switch.  
  
 L'exemple suivant génère l'erreur C2050 :  
  
```  
// C2050.cpp  
int main() {  
   int a = 1;  
   switch ("a") {   // C2050  
      case 1:  
         a = 0;  
      default:  
         a = 2;  
   }  
}  
```  
  
 Résolution possible :  
  
```  
// C2050b.cpp  
int main() {  
   int a = 1;  
   switch (a) {  
      case 1:  
         a = 0;  
      default:  
         a = 2;  
   }  
}  
```