---
title: "Erreur du compilateur C2085 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2085"
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : ne figure pas dans la liste de paramètres formels  
  
 L'identificateur a été déclaré dans une définition de fonction mais pas dans la liste de paramètres formels. \(C ANSI seulement\)  
  
 L'exemple suivant génère l'erreur C2085 :  
  
```  
// C2085.c  
void func1( void )  
int main( void ) {}   // C2085  
```  
  
 Résolution possible :  
  
```  
// C2085b.c  
void func1( void );  
int main( void ) {}  
```  
  
 Sans le point\-virgule, `func1()` se présente comme une définition de fonction, et non pas comme un prototype, donc `main` est défini à l'intérieur de `func1()`, ce qui génère l'erreur C2085 pour l'identificateur `main`.