---
title: "Erreur du compilateur C3610 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3610"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3610"
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3610
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

TypeValeur : le type valeur doit être 'boxed' pour que la méthode 'méthode' puisse être appelée  
  
 Par défaut, un type valeur n'est pas sur le tas managé.  Avant de pouvoir appeler des méthodes depuis les classes de runtime .NET, comme `Object`, vous devez déplacer le type valeur vers le tas managé.  
  
 L'erreur C3610 n'est accessible qu'à l'aide de **\/clr:oldSyntax**.  
  
 L'exemple suivant génère l'erreur C3610 :  
  
```  
// C3610.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__value class A {};  
  
int main() {  
   A a;  
   a.GetType(); // C3610  
  
   // OK  
   __box A* ovar = __box(a);  
   ovar->GetType();  
}  
```