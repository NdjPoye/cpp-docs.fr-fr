---
title: "Erreur du compilateur C3634 | Microsoft Docs"
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
  - "C3634"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3634"
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3634
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : impossible de définir une méthode abstraite d'une classe managée ou WinRT  
  
 Une méthode abstraite peut être déclarée dans une classe managée ou WinRT, mais elle ne peut pas être définie.  
  
 L'exemple suivant génère l'erreur C3634 :  
  
```  
// C3634.cpp  
// compile with: /clr  
ref class C {  
   virtual void f() = 0;  
};  
  
void C::f() {   // C3634 - don't define managed class' pure virtual method  
}  
```  
  
 **Extensions managées pour C\+\+**  
  
 L'exemple suivant génère l'erreur C3634 :  
  
```  
// C3634b.cpp  
// compile with: /clr:oldSyntax /LD  
#using <mscorlib.dll>  
  
__gc class C {  
   virtual void f() = 0;  
};  
  
void C::f() {   // C3634 - don't define managed class' pure virtual method  
}  
```