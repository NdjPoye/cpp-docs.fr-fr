---
title: "Erreur du compilateur C3149 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3149"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3149"
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Erreur du compilateur C3149
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : impossible d'utiliser ce type ici sans 'char' de niveau supérieur  
  
 Une déclaration n'a pas été spécifiée correctement.  
  
 Par exemple, il se peut que vous ayez défini un type CLR au niveau de la portée globale et tenté de créer une variable du type dans le cadre de la définition.  Comme les variables globales de types CLR ne sont pas autorisées, le compilateur génère l'erreur C3149.  
  
 Pour résoudre cette erreur, déclarez les variables de types CLR à l'intérieur d'une définition de fonction ou de type.  
  
 L'exemple suivant génère l'erreur C3149 :  
  
```  
// C3149.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   // declare an array of value types   
   array< Int32 ^> IntArray;   // C3149  
   array< Int32>^ IntArray2;   // OK  
}  
```  
  
 L'exemple suivant génère l'erreur C3149 :  
  
```  
// C3149b.cpp  
// compile with: /clr /c  
delegate int MyDelegate(const int, int);  
void Test1(MyDelegate m) {}   // C3149  
void Test2(MyDelegate ^ m) {}   // OK  
```  
  
 **Extensions managées pour C\+\+**  
  
 Un objet managé n'a pas été correctement utilisé.  
  
 L'exemple suivant génère l'erreur C3149 :  
  
```  
// C3149c.cpp  
// compile with: /clr:oldSyntax  
__gc class A {};  
  
int main() {  
   A a = new A;   // C3149  
   A *a = new A;   // OK  
}  
```