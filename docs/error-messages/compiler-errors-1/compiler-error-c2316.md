---
title: "Erreur du compilateur C2316 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2316"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2316"
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Erreur du compilateur C2316
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'exception' : ne peut pas être intercepté en tant que destructeur et\/ou le constructeur de copie est inaccessible  
  
 Une exception a été interceptée par valeur ou par référence, mais le constructeur de copie et\/ou l’opérateur d’assignation étaient inaccessibles.  
  
 Ce code a été accepté par le compilateur de la version précédente mais génère maintenant une erreur.  
  
## Exemple  
 L’exemple suivant génère l’erreur C2316 :  
  
```  
// C2316.cpp // compile with: /EHsc #include <stdio.h> extern "C" int printf_s(const char*, ...); struct B { public: B() {} // Delete the following line to resolve. private: // copy constructor B(const B&) { } }; void f(const B&) { } int main() { try { B aB; f(aB); } catch (B b) {   // C2316 printf_s("Caught an exception!\n"); } }  
```