---
title: "Erreur du compilateur C2448 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2448"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2448"
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2448
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : l'initialiseur de style fonction semble être une définition de fonction  
  
 La définition de la fonction est incorrecte.  
  
 Cette erreur peut être provoquée par une liste formelle en langage C à l'ancien format.  
  
 L'exemple suivant génère l'erreur C2448 :  
  
```  
// C2448.cpp  
void func(c)  
   int c;  
{}   // C2448  
```