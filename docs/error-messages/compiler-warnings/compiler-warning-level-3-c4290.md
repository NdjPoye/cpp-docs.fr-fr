---
title: "Avertissement du compilateur (niveau 3) C4290 | Microsoft Docs"
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
  - "C4290"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4290"
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4290
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécification d'exception C\+\+ ignorée sauf pour indiquer qu'une fonction n'est pas \_\_declspec\(nothrow\)  
  
 Une fonction est déclarée avec une spécification d'exception, ce que Visual C\+\+ accepte mais n'implémente pas.  Le code avec spécification d'exception ignoré lors de la compilation peut nécessiter une nouvelle compilation et édition de liens pour pouvoir être réutilisé dans des versions ultérieures prenant en charge les spécifications d'exception.  
  
 Pour plus d'informations, consultez [Spécifications d'exception \(throw\)](../../cpp/exception-specifications-throw-cpp.md).  
  
 Vous pouvez éviter cet avertissement par le pragma [warning](../../preprocessor/warning.md) :  
  
```  
#pragma warning( disable : 4290 )  
```  
  
 L'exemple de code suivant génère C4290 :  
  
```  
// C4290.cpp  
// compile with: /EHs /W3 /c  
void f1(void) throw(int) {}   // C4290  
  
// OK  
void f2(void) throw() {}  
void f3(void) throw(...) {}  
```