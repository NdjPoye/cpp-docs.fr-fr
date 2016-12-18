---
title: "Avertissement du compilateur (niveau 1) C4584 | Microsoft Docs"
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
  - "C4584"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4584"
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4584
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe1' : la classe de base 'classe2' est déjà une classe de base de 'classe3'  
  
 La classe définie hérite de deux classes, et l'une d'elles hérite de l'autre.  Par exemple :  
  
```  
// C4584.cpp  
// compile with: /W1 /LD  
class A {  
};  
  
class B : public A {  
};  
  
class C : public A, public B { // C4584  
};  
```  
  
 Dans ce cas, un avertissement est émis sur la classe C car elle hérite à la fois de la classe A et de la classe B, laquelle hérite également de la classe A.  Cet avertissement sert à vous rappeler que vous devez complètement qualifier l'utilisation des membres de ces classes de base, sinon l'ambiguïté quant au membre de classe auquel vous faites référence provoque une erreur du compilateur.