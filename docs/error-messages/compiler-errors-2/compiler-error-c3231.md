---
title: "Erreur du compilateur C3231 | Microsoft Docs"
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
  - "C3231"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3231"
ms.assetid: fe5dc352-e634-45fa-9534-3da176294c98
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3231
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg' : l'argument de type de modèle ne peut pas utiliser de paramètre de type générique  
  
 Les modèles sont instanciés au moment de la compilation, mais les génériques le sont au moment de l'exécution.  Par conséquent, il n'est pas possible de générer du code générique pouvant appeler le modèle, car ce dernier ne peut pas être instancié au moment de l'exécution lorsque le type générique est enfin connu.  
  
 L'exemple suivant génère l'erreur C3231 :  
  
```  
// C3231.cpp  
// compile with: /clr /LD  
template <class T> class A;  
  
generic <class T>  
ref class C {  
   void f() {  
      A<T> a;   // C3231  
   }  
};  
```