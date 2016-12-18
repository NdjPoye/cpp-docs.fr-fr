---
title: "Erreur du compilateur C2360 | Microsoft Docs"
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
  - "C2360"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2360"
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2360
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'initialisation de 'identificateur' est ignorée par l'étiquette 'case'  
  
 L'initialisation de `identifier` peut être ignorée dans une instruction `switch`.  Vous ne pouvez pas aller au\-delà d'une déclaration avec un initialiseur si la déclaration ne figure pas dans un bloc. \(À moins d'être déclarée dans un bloc, la variable se trouve dans la portée jusqu'à la fin de l'instruction `switch`.\)  
  
 L'exemple suivant génère l'erreur C2360 :  
  
```  
// C2360.cpp  
int main() {  
   int x = 0;  
   switch ( x ) {  
   case 0 :  
      int i = 1;  
      { int j = 1; }  
   case 1 :   // C2360  
      int k = 1;  
   }  
}  
```  
  
 Résolution possible :  
  
```  
// C2360b.cpp  
int main() {  
   int x = 0;  
   switch ( x ) {  
   case 0 :  
      { int j = 1; int i = 1;}  
   case 1 :  
      int k = 1;  
   }  
}  
```