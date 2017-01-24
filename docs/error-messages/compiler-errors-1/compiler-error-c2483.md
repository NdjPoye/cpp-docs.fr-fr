---
title: "Erreur du compilateur C2483 | Microsoft Docs"
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
  - "C2483"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2483"
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2483
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : un objet avec constructeur ou destructeur ne peut pas être déclaré comme 'thread'  
  
 Les variables déclarées avec l'attribut `thread` ne peuvent être initialisées avec un constructeur ou toute autre expression demandant une évaluation au moment de l'exécution.  Une expression statique est requise pour initialiser les données `thread`.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2483 :  
  
```  
// C2483.cpp  
// compile with: /c  
__declspec(thread) struct A {  
   A(){}  
   ~A(){}  
} aa;   // C2483 error  
  
__declspec(thread) struct B {} b;   // OK  
```  
  
## Voir aussi  
 [thread](../../cpp/thread.md)