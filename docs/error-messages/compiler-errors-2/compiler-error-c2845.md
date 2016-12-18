---
title: "Erreur du compilateur C2845 | Microsoft Docs"
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
  - "C2845"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2845"
ms.assetid: 31b28ee9-978f-403b-94d8-dbaacd24cce0
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2845
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : opération arithmétique de pointeur non autorisée sur ce type  
  
 Vous ne pouvez pas incrémenter le pointeur vers une classe managée.  
  
 **Extensions managées pour C\+\+**  
  
 Vous ne pouvez pas mettre en œuvre le pointeur vers une classe [\_\_gc](../../misc/gc.md).  En outre, les opérateurs de chaîne ne sont valides qu'avec **\/clr** \(pas avec **\/clr:oldSyntax**\).  
  
 L'exemple suivant génère l'erreur C2845 :  
  
```  
// C2845b.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
__gc class X {};  
  
int main() {  
   X *pX = new X;  
   pX++;   // C2845  
  
   String * a = new String("abc");  
   String * b = new String("def");  
   Console::WriteLine(a + b);   // C2845 not with /clr:oldSyntax  
}  
```