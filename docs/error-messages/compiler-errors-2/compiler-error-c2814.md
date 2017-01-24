---
title: "Erreur du compilateur C2814 | Microsoft Docs"
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
  - "C2814"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2814"
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2814
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : un type natif ne peut pas être imbriqué dans un type managé ou WinRT 'type'  
  
## Exemple  
 Un type natif ne peut pas être imbriqué dans un type CLR ou WinRT.  L'exemple suivant génère l'erreur C2814 et montre comment la corriger.  
  
```  
// C2814.cpp  
// compile with: /clr /c  
ref class A {  
   class B {};   // C2814  
   ref class C {};   // OK  
};  
```  
  
## Exemple  
 À l'aide des extensions managées pour C\+\+, vous devez spécifier explicitement le « caractère managé » d'un type incorporé à l'aide d'un des mots clés suivants : [\_\_gc](../../misc/gc.md), [\_\_nogc](../../misc/nogc.md) ou [\_\_value](../../misc/value.md).  
  
 L'exemple suivant génère l'erreur C2814 et montre comment la corriger.  
  
```  
// C2814_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc class A {  
   class B {};   // C2814  
   __gc class C {};   // OK  
};  
```