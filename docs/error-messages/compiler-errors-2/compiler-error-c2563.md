---
title: "Erreur du compilateur C2563 | Microsoft Docs"
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
  - "C2563"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2563"
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2563
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

incompatibilité dans la liste de paramètres formels  
  
 La liste de paramètres formels d'une fonction \(ou un pointeur vers une fonction\) ne correspond pas à celle d'une autre fonction \(ou un pointeur vers une fonction membre\).  Par conséquent, l'assignation des fonctions ou des pointeurs ne peut avoir lieu.  
  
 L'exemple suivant génère l'erreur C2563 :  
  
```  
// C2563.cpp  
void func( int );  
void func( int, int );  
int main() {  
   void *fp();  
   fp = func;   // C2563  
}  
```