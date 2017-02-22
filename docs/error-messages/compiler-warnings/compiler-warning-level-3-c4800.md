---
title: "Avertissement du compilateur (niveau 3) C4800 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4800"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4800"
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 3) C4800
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : valeur forcée à la valeur booléenne 'true' ou 'false' \(avertissement sur les performances\)  
  
 Cet avertissement est généré lorsqu'une valeur non `bool` est assignée ou forcée dans le type `bool`.  Ce message est généralement provoqué par l'assignation de variables `int` à des variables `bool` lorsque les variables `int` ne contiennent que des valeurs **true** et **false** et pourraient être redéclarées comme type `bool`.  Si vous ne pouvez pas réécrire l'expression de manière à utiliser le type `bool`, vous pouvez alors ajouter "`!=0`" à celle\-ci, ce qui lui donne le type `bool`.  Le casting de l'expression en un type `bool` ne désactivera pas l'avertissement qui est dû au design.  
  
 L'exemple suivant génère l'erreur C4800 :  
  
```  
// C4800.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
  
   // try..  
   // bool i = 0;  
  
   bool j = i;   // C4800  
   j++;  
}  
```