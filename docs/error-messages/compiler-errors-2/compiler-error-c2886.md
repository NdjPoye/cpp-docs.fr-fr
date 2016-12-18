---
title: "Erreur du compilateur C2886 | Microsoft Docs"
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
  - "C2886"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2886"
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2886
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe::identificateur' : un symbole ne peut pas être utilisé dans la déclaration using d'un membre  
  
 Une déclaration `using` emploie un symbole comme le nom d'un espace de noms.  Une déclaration `using` sert à déclarer les membres de la classe de base.  
  
 L'exemple suivant génère l'erreur C2886 :  
  
```  
// C2886.cpp  
// compile with: /c  
namespace Z {  
    int i;  
}  
  
class B {  
protected:  
    int i;  
};  
  
class D : public B {  
    // Error: Z is a namespace  
    using Z::i;   // C2886  
  
    // OK: B is a base class  
    using B::i;  
};  
```