---
title: "Erreur du compilateur C3808 | Microsoft Docs"
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
  - "C3808"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3808"
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3808
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : une classe avec l'attribut ComImport ne peut pas définir de membre 'membre', seules les fonctions abstract ou dllimport sont autorisées  
  
 Un type dérivé de <xref:System.Runtime.InteropServices.ComImportAttribute> ne peut pas définir `member`.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3808 :  
  
```  
// C3808.cpp  
// compile with: /c /clr:pure user32.lib  
using namespace System::Runtime::InteropServices;  
  
[System::Runtime::InteropServices::ComImportAttribute()]  
ref struct S1 {  
   int f() {}   // C3808  
   virtual int g() abstract;   // OK  
  
   [DllImport("msvcrt.dll")]  
   int printf(System::String ^, int i);   // OK  
};  
```