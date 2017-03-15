---
title: "Erreur du compilateur C2523 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2523"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2523"
ms.assetid: 7951b700-8f37-45a0-beb4-a79ae0ced72e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2523
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe::~identificateur' : balise de destructeur\/finaliseur non correcte  
  
 Le nom du destructeur doit être le nom de la classe précédé d'un tilde \(`~`\).  Le constructeur et le destructeur sont les seuls membres dont le nom est identique à celui de la classe.  
  
 L'exemple suivant génère l'erreur C2523 :  
  
```  
// C2523.cpp  
// compile with: /c  
class A {  
   ~B();    // C2523  
   ~A();   // OK  
};  
```