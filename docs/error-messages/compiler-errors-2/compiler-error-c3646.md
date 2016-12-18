---
title: "Erreur du compilateur C3646 | Microsoft Docs"
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
  - "C3646"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3646"
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3646
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'spécificateur' : spécificateur de substitution inconnu  
  
 Le compilateur a détecté un jeton à l'emplacement auquel devait se trouver un spécificateur de substitution, mais le compilateur n'a pas pu le reconnaître.  
  
 Pour plus d'informations, consultez [Spécificateurs de substitution](../../windows/override-specifiers-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C3646 :  
  
```  
// C3646.cpp  
// compile with: /clr /c  
ref class C {  
   void f() unknown;   // C3646  
   // try the following line instead  
   // virtual void f() abstract;  
};  
```