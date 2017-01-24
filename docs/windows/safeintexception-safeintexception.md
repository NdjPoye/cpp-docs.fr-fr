---
title: "SafeIntException::SafeIntException | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeIntException"
  - "SafeIntException.SafeIntException"
  - "SafeIntException::SafeIntException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeIntException, constructeur"
ms.assetid: 8e5a0c24-a56b-4c80-9ee8-876604b1e7dc
caps.latest.revision: 6
caps.handback.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeIntException::SafeIntException
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée un objet `SafeIntException`.  
  
## Syntaxe  
  
```  
SafeIntException();  
  
SafeIntException(  
   SafeIntError code  
);  
```  
  
#### Paramètres  
 \[in\] `code`  
 An enumerated data value that describes the error that occurred.  
  
## Notes  
 The possible values for `code` are defined in the file Safeint.h.  For convenience, the possible values are also listed here.  
  
-   `SafeIntNoError`  
  
-   `SafeIntArithmeticOverflow`  
  
-   `SafeIntDivideByZero`  
  
## Configuration requise  
 **Header:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## Voir aussi  
 [Bibliothèque SafeInt](../windows/safeint-library.md)   
 [SafeIntException, classe](../windows/safeintexception-class.md)   
 [SafeInt, classe](../windows/safeint-class.md)