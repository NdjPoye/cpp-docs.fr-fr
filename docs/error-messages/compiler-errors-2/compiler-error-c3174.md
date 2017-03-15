---
title: "Erreur du compilateur C3174 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3174"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3174"
ms.assetid: fe6b3b5a-8196-485f-a45f-0b2e51df4086
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3174
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

attribut module non spécifié  
  
 Un programme qui utilise des attributs Visual C\+\+ n'utilise pas également l'attribut [module](../../windows/module-cpp.md) qui est requis dans tout programme qui utilise des attributs.  
  
 L'exemple suivant génère l'erreur C3174 :  
  
```  
// C3174.cpp  
// C3174 expected  
// uncomment the following line to resolve this C3174  
// [module(name="x")];  
[export]  
struct S  
{  
   int i;  
};  
  
int main()  
{  
}  
```