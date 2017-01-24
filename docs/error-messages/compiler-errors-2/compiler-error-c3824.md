---
title: "Erreur du compilateur C3824 | Microsoft Docs"
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
  - "C3824"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3824"
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3824
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : ce type ne peut pas apparaître dans ce contexte \(paramètre de fonction, type de retour ou membre static\)  
  
 Les pointeurs épingle ne peuvent pas être des paramètres de fonction, des types de retour ou des membres `static` déclarés.  
  
 L'exemple suivant génère l'erreur C3824 :  
  
```  
// C3824a.cpp  
// compile with: /clr /c  
void func() {  
   static pin_ptr<int> a; // C3824  
   pin_ptr<int> b; // OK  
}  
```  
  
 **Extensions managées pour C\+\+**  
  
 Les pointeurs locaux déclarés avec le mot clé `__pin` ne peuvent pas être déclarés `static` et ne peuvent pas être des pointeurs intérieurs.  
  
 L'exemple suivant génère l'erreur C3824 :  
  
```  
// C3824b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
  
__gc struct A {};  
  
void func() {  
   static A __pin* a;   // C3824  
   A __pin* b;   // OK  
}  
```