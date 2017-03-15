---
title: "Erreur du compilateur C2361 | Microsoft Docs"
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
  - "C2361"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2361"
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2361
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'initialisation de 'identificateur' est ignorée par l'étiquette 'default'  
  
 L'initialisation de `identifier` peut être ignorée dans une instruction `switch`.  Vous ne pouvez pas aller au\-delà d'une déclaration avec un initialiseur si la déclaration ne figure pas dans un bloc. \(À moins d'être déclarée dans un bloc, la variable se trouve dans la portée jusqu'à la fin de l'instruction `switch`.\)  
  
 L'exemple suivant génère l'erreur C2361 :  
  
```  
// C2361.cpp  
void func( void ) {  
   int x;  
   switch (x) {  
   case 0 :  
      int i = 1;  
      { int j = 1; }  
   default :   // C2361 error  
      int k = 1;  
   }  
}  
```  
  
 Résolution possible :  
  
```  
// C2361b.cpp  
// compile with: /c  
void func( void ) {  
   int x = 0;  
   switch (x) {  
   case 0 :  
      { int j = 1; int i = 1;}  
   default :  
      int k = 1;  
   }  
}  
```