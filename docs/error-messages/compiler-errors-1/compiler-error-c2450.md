---
title: "Erreur du compilateur C2450 | Microsoft Docs"
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
  - "C2450"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2450"
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2450
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

expression de switch de type 'type' non conforme  
  
 L'expression de `switch` s'évalue en un type non valide.  Elle doit s'évaluer en un type d'entier ou de classe dont la conversion avec un type d'entier est sans ambiguïté.  Si l'expression s'évalue en un type défini par l'utilisateur, vous devez fournir un opérateur de conversion.  
  
 L'exemple suivant génère l'erreur C2450 :  
  
```  
// C2450.cpp  
class X {  
public:  
   int i;  
} x;  
  
class Y {  
public:  
   int i;  
   operator int() { return i; }   // conversion operator  
} y;  
  
int main() {  
   int j = 1;  
   switch ( x ) {   // C2450, x is not type int  
   // try the following line instead  
   // switch ( y ) {  
      default:  ;  
   }  
}  
```