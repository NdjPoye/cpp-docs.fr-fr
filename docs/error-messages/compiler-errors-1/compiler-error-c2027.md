---
title: "Erreur du compilateur C2027 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2027"
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

utilisation du type non défini 'type'  
  
 Un type ne peut pas être utilisé tant qu'il n'est pas défini.  Pour corriger l'erreur, vérifiez que le type est complètement défini avant de le référencer.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2027 :  
  
```  
// C2027.cpp  
class C;  
class D {  
public:  
   void func() {  
   }  
};  
  
int main() {  
   C *pC;  
   pC->func();   // C2027  
  
   D *pD;  
   pD->func();  
}  
```  
  
## Exemple  
 Il est possible de déclarer un pointeur vers un type déclaré, mais indéfini.  Cependant, Visual C\+\+ n'autorise pas de référence à un type indéfini.  
  
 L'exemple suivant génère l'erreur C2027 :  
  
```  
// C2027_b.cpp  
class A;  
A& CreateA();  
  
class B;  
B* CreateB();  
  
int main() {  
   CreateA();   // C2027  
   CreateB();   // OK  
}  
```