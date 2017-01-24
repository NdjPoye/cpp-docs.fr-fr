---
title: "Compiler Error C3386 | Microsoft Docs"
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
  - "C3386"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3386"
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C3386
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : \_\_declspec\(dllexport\)\/\_\_declspec\(dllimport\) ne peut pas être appliqué à un type managé ou WinRT  
  
 Les modificateurs `dllimport` et [dllexport](../../cpp/dllexport-dllimport.md) `__declspec` ne sont pas valides sur un type managé ou Windows Runtime.  
  
 L'exemple suivant génère l'erreur C3386 et montre comment la corriger :  
  
```  
// C3386.cpp  
// compile with: /clr /c  
ref class __declspec(dllimport) X1 {   // C3386  
// try the following line instead  
// ref class X1 {  
};  
```