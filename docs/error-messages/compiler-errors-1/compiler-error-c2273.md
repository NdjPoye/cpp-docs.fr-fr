---
title: "Erreur du compilateur C2273 | Microsoft Docs"
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
  - "C2273"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2273"
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2273
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : non conforme à droite de l'opérateur '\-\>'  
  
 Un type apparaît comme l'opérande de droite d'un opérateur `->`.  
  
 Cette erreur peut être provoquée si vous tentez d'accéder à une conversion de type définie par l'utilisateur.  Utilisez le mot clé `operator` entre \-\> et `type`.  
  
 L'exemple suivant génère l'erreur C2273 :  
  
```  
// C2273.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
int main() {  
   MyClass * ClassPtr = new MyClass;  
   int i = ClassPtr->int();   // C2273  
   int j = ClassPtr-> operator int();   // OK  
}  
```