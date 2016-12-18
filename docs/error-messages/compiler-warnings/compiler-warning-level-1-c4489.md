---
title: "Avertissement du compilateur (niveau 1) C4489 | Microsoft Docs"
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
  - "C4489"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4489"
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4489
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'spécificateur' : non autorisé sur la méthode d'interface 'méthode' ; les spécificateurs de substitution sont uniquement autorisés sur les méthodes des classes ref et value  
  
 Un mot clé spécificateur a été utilisé incorrectement dans une méthode d'interface.  
  
 Pour plus d'informations, consultez [Spécificateurs de substitution](../../windows/override-specifiers-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4489 :  
  
```  
// C4489.cpp  
// compile with: /clr /c /W1  
public interface class I {   
   void f() new;   // C4489  
   virtual void b() override;   // C4489  
  
   void g();   // OK  
};  
```