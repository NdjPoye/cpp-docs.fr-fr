---
title: "Erreur du compilateur C3910 | Microsoft Docs"
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
  - "C3910"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3910"
ms.assetid: cfcbe620-b463-463b-95ea-2d60ad33ebb5
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3910
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'événement' : doit définir la 'méthode' membre  
  
 Un événement a été défini, mais ne contenait pas la méthode d'accesseur spécifiée requise.  
  
 Pour plus d'informations, consultez [event](../../windows/event-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C3910 :  
  
```  
// C3910.cpp  
// compile with: /clr /c  
delegate void H();  
ref class X {  
   event H^ E {  
      // uncomment the following lines  
      // void add(H^) {}  
      // void remove( H^ h ) {}  
      // void raise( ) {}  
   };   // C3910  
  
   event H^ E2; // OK data member  
};  
```