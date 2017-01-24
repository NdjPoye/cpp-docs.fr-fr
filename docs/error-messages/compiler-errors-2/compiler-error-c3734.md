---
title: "Erreur du compilateur C3734 | Microsoft Docs"
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
  - "C3734"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3734"
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3734
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : une classe managée ou WinRT ne peut pas être une coclasse  
  
 L'attribut [coclasse](../../windows/coclass.md) ne peut pas être utilisé avec des classes managées ou WinRT.  
  
 L'exemple suivant génère l'erreur C3734 et montre comment la corriger :  
  
```  
// C3734.cpp  
// compile with: /clr /c  
[module(name="x")];  
  
[coclass]  
ref class CMyClass {   // C3734 remove the ref keyword to resolve  
};  
```  
  
 L'exemple suivant génère l'erreur C3734 et montre comment la corriger :  
  
```  
// C3734_b.cpp  
// compile with: /clr:oldSyntax /c  
[module(name="x")];  
  
[coclass]  
__gc class CMyClass {   // C3734 remove the __gc keyword to resolve  
};  
```