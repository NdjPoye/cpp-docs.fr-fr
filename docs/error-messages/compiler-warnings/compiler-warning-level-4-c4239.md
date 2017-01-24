---
title: "Avertissement du compilateur (niveau 4) C4239 | Microsoft Docs"
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
  - "C4239"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4239"
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4239
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : 'jeton' : conversion de 'type' en 'type'  
  
 Cette conversion de type n'est pas autorisée par la norme C\+\+, mais elle est autorisée ici en tant qu'extension.  Cet avertissement est toujours suivi au moins d'une ligne d'explication décrivant l'infraction à la règle du langage.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4239 :  
  
```  
// C4239.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
void func(void) {  
   C & rC = C();   // C4239  
   const C & rC2 = C();   // OK  
   rC2;  
}  
```  
  
## Exemple  
 La conversion de type intégral en type enum n'est pas réellement permise.  
  
 L'exemple suivant génère l'erreur C4239 :  
  
```  
// C4239b.cpp  
// compile with: /W4 /c  
enum E { value };   
struct S {   
   E e : 2;   
} s = { 5 };   // C4239   
// try the following line instead  
// } s = { (E)5 };  
```