---
title: "Erreur du compilateur C3625 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3625"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3625"
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Erreur du compilateur C3625
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type\_natif' : un type natif ne peut pas dériver d'un type managé ou WinRT 'type'  
  
 Une classe native ne peut pas hériter d'une classe managée ou WinRT.  Pour plus d'informations, consultez [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C3625 :  
  
```  
// C3625.cpp  
// compile with: /clr /c  
ref class B {};  
class D : public B {};   // C3625 cannot inherit from a managed class  
```  
  
 L'exemple suivant génère l'erreur C3625 :  
  
```  
// C3625_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc class B {};  
class D : public B {};   // C3625  cannot inherit from a managed class  
```