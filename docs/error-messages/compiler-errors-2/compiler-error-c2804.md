---
title: "Erreur du compilateur C2804 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2804"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2804"
ms.assetid: b066e563-cca4-450c-8ba7-3b0d7a89f3ea
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2804
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

trop de paramètres pour l'opérateur binaire 'operator opérateur'  
  
 La fonction membre de l'opérateur binaire surchargé est déclarée avec plusieurs paramètres.  Le paramètre de premier opérande d'une fonction membre d'opérateur binaire, dont le type est le type englobant de l'opérateur, est implicite.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2804 et montre comment la corriger.  
  
```  
// C2804.cpp  
// compile by using: cl /c /W4 C2804.cpp  
class X {  
public:  
   X& operator+= (const X &left, const X &right);   // C2804  
   X& operator+= (const X &right);   // OK - left operand implicitly *this  
};  
  
int main() {  
   X x, y;  
   x += y;   // equivalent to x.operator+=(y)  
}  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C2804 et montre comment la corriger.  
  
```  
// C2804_2.cpp  
// compile with: /clr /c  
ref struct Y {  
   Y^ operator +(Y^ hY, int i);   // C2804  
   static Y^ operator +(Y^ hY, int i);   // OK  
   Y^ operator +(int i);   // OK  
};  
```