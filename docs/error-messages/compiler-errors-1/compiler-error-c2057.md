---
title: "Erreur du compilateur C2057 | Microsoft Docs"
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
  - "C2057"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2057"
ms.assetid: 038a99d6-1f5a-42fa-8449-03b4ff11ee0b
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2057
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

expression constante attendue  
  
 Le contexte requiert une expression constante, une expression dont la valeur est connue au moment de la compilation.  
  
 Le compilateur doit connaître la taille d'un type au moment de la compilation pour allouer de l'espace pour une instance de ce type.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2057 et montre comment la corriger :  
  
```  
// C2057.cpp  
int i;  
int b[i];   // C2057 - value of i is unknown at compile time  
int main() {  
   const int i = 8;  
   int b[i]; // OK - value of i is fixed and known to compiler  
}  
```  
  
## Exemple  
 C possède des règles plus restrictives pour les expressions constantes.  L'exemple suivant génère l'erreur C2057 et montre comment la corriger :  
  
```  
// C2057b.c  
#define ArraySize1 10  
int main() {   
   const int ArraySize2 = 10;   
   int h[ArraySize2];   // C2057 - C does not allow variables here  
   int h[ArraySize1];   // OK - uses preprocessor constant  
}  
```