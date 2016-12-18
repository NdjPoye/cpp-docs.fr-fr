---
title: "Erreur du compilateur C2690 | Microsoft Docs"
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
  - "C2690"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2690"
ms.assetid: f165a806-14bd-4942-99b7-8a9fc7dea227
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2690
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : impossible d'effectuer une opération arithmétique de pointeur sur un tableau managé ou WinRT  
  
 Une opération arithmétique de pointeur n'est pas autorisée sur un tableau managé ou WinRT.  Utilisez la notation d'index de tableau pour parcourir le tableau.  
  
 **Extensions managées pour C\+\+**  
  
 Une opération arithmétique de pointeur n'est pas autorisée sur un tableau [\_\_gc](../../misc/gc.md).  Utilisez la notation d'index de tableau pour parcourir le tableau.  
  
 L'exemple suivant génère l'erreur C2690 :  
  
```  
// C2690b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
int main() {  
   String* x[] = new String*[10];  
   x[0] = "test";  
   Console::WriteLine(x[0]);  
   x++;   // C2690  
}  
```