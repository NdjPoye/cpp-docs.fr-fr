---
title: "Erreur du compilateur C2274 | Microsoft Docs"
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
  - "C2274"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2274"
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2274
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : non conforme à droite de l'opérateur '.'  
  
 Un type apparaît comme l'opérande de droite d'un opérateur d'accès à un membre \(.\).  
  
 Cette erreur peut être provoquée si vous tentez d'accéder à une conversion de type définie par l'utilisateur.  Utilisez le mot clé `operator` entre le point et le `type`.  
  
 L'exemple suivant génère l'erreur C2286 :  
  
```  
// C2274.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
  
int main() {  
   MyClass ClassName;  
   int i = ClassName.int();   // C2274  
   int j = ClassName.operator int();   // OK  
}  
```