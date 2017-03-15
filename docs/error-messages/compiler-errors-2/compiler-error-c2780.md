---
title: "Erreur du compilateur C2780 | Microsoft Docs"
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
  - "C2780"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2780"
ms.assetid: 423793d8-a3b2-4f35-85f8-ae1d043e2b69
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2780
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'déclaration' : N arguments attendus \- M fournis  
  
 Un modèle de fonction a trop peu d'arguments ou trop d'arguments.  
  
 L'exemple suivant génère l'erreur C2780 et montre comment la corriger :  
  
```  
// C2780.cpp  
template<typename T>  
void f(T, T){}  
  
int main() {  
   f(1);  // C2780  
   // try the following line instead  
   // f(1,2);  
}  
```