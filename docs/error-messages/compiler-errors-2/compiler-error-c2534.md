---
title: "Erreur du compilateur C2534 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2534"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2534"
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2534
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : le constructeur ne peut pas retourner de valeur  
  
 Un constructeur ne peut pas avoir de valeur ou de type de retour \(pas même un type de retour `void`\).  
  
 Cette erreur peut être résolue en supprimant l'instruction `return` de la définition d'un constructeur.  
  
 L'exemple suivant génère l'erreur C2534 :  
  
```  
// C2534.cpp  
class A {  
public:  
   int i;  
   A() { return i; }   // C2534  
};  
```