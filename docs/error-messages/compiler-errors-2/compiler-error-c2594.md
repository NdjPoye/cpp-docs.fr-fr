---
title: "Erreur du compilateur C2594 | Microsoft Docs"
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
  - "C2594"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2594"
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2594
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : conversions ambiguës de 'type1' en 'type2'  
  
 Aucune conversion de *type1* en *type2* n'a été plus directe qu'une autre.  Nous suggérons deux solutions possibles à la conversion de *type1* en *type2*.  La première option consiste à définir une conversion directe de *type1* en *type2*, et la deuxième option consiste en la spécification d'une séquence de conversions de *type1* en *type2*.  
  
 L'exemple suivant génère l'erreur C2594.  Pour résoudre cette erreur, nous suggérons une séquence de conversions :  
  
```  
// C2594.cpp  
// compile with: /c  
struct A{};  
struct I1 : A {};  
struct I2 : A {};  
struct D : I1, I2 {};  
  
A *f (D *p) {  
   return (A*) (p);    // C2594  
  
// try the following line instead  
// return static_cast<A *>(static_cast<I1 *>(p));  
}  
```