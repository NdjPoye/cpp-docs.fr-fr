---
title: "Erreur du compilateur C2447 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2447"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2447"
ms.assetid: d1bd6e9a-ee42-4510-ae5e-6b0378f7b931
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C2447
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'{' : en\-tête de fonction manquant \(liste formelle à l'ancien format ?\)  
  
 Le compilateur a rencontré une accolade ouvrante inattendue au niveau de l'étendue globale.  Dans la plupart des cas, cela est dû à un en\-tête de fonction incorrect, une déclaration mal placée ou un point\-virgule égaré.  Pour résoudre ce problème, vérifiez que l'accolade ouvrante suit un en\-tête de fonction correct, et qu'elle n'est pas précédée d'une déclaration ou d'un point\-virgule égaré.  
  
 Cette erreur peut également être provoquée par une liste d'arguments formels en langage C à l'ancien format.  Pour résoudre ce problème, refactorisez la liste d'arguments afin d'utiliser le style moderne, c'est\-à\-dire entre parenthèses.  
  
 L'exemple suivant génère l'erreur C2447 :  
  
```  
// C2447.cpp  
int c;  
{}       // C2447  
```