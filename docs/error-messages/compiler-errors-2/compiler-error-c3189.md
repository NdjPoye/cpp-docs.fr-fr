---
title: "Erreur du compilateur C3189 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3189"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3189"
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C3189
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'typeid\<déclarateur de type abstrait\>': cette syntaxe n'est plus prise en charge, utilisez ::typeid à la place  
  
 Une forme obsolète de [typeid](../../windows/typeid-cpp-component-extensions.md) a été utilisée ; utilisez la nouvelle forme.  
  
 L'exemple suivant génère l'erreur C3189 :  
  
```  
// C3189.cpp  
// compile with: /clr  
int main() {  
   System::Type^ t  = typeid<System::Object>;   // C3189  
   System::Type^ t2  = System::Object::typeid;   // OK  
}  
```