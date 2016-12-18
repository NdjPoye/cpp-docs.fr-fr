---
title: "Erreur du compilateur C3890 | Microsoft Docs"
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
  - "C3890"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3890"
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3890
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : vous ne pouvez pas prendre l'adresse d'une donnée membre littérale  
  
 Une donnée membre littérale existe sur le tas récupéré par le garbage collector.  Un objet situé sur le tas récupéré par le garbage collector peut être déplacé ; par conséquent, la prise de son adresse n'est pas utile.  
  
 L'exemple suivant génère l'erreur C3890 :  
  
```  
// C3890.cpp  
// compile with: /clr  
ref struct Y1 {  
   literal int staticConst = 9;  
};  
  
int main() {  
   int p = &Y1::staticConst;   // C3890  
   int p2 = Y1::staticConst;   // OK  
}  
```