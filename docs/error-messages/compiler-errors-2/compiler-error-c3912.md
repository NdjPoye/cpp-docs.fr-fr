---
title: "Erreur du compilateur C3912 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3912"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3912"
ms.assetid: 674e050c-11fb-4db1-8bdf-a3e95b41161d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3912
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'événement' : l'événement doit être de type délégué  
  
 Un événement a été déclaré, mais ne possédait pas le type correct.  
  
 Pour plus d'informations, consultez [event](../../windows/event-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C3912 :  
  
```  
// C3912.cpp  
// compile with: /clr  
delegate void H();  
ref class X {  
   event int Ev;   // C3912  
   event H^ Ev2;   // OK  
};  
```