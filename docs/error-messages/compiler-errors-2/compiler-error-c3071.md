---
title: "Erreur du compilateur C3071 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3071"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3071"
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3071
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'opérateur 'opérateur' ne peut être appliqué qu'à une instance d'une classe ref ou d'un type valeur  
  
 Un opérateur CLR ne peut pas être utilisé sur un type natif.  L'opérateur peut être utilisé sur une classe ref ou un struct ref \(un type valeur\), mais pas sur un type natif tel que int ni sur un alias pour un type natif tel que System::Int32.  Ces types ne peuvent pas être convertis à partir de code C\+\+ d'une manière faisant référence à la variable native, si bien que l'opérateur ne peut pas être utilisé.  
  
 Pour plus d'informations, consultez [Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3071.  
  
```  
// C3071.cpp  
// compile with: /clr  
class N {};  
ref struct R {};  
  
int main() {  
   N n;  
   %n;   // C3071  
  
   R r;  
   R ^ r2 = %r;   // OK  
}  
```