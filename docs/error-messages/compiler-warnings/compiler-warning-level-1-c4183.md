---
title: "Avertissement du compilateur (niveau 1) C4183 | Microsoft Docs"
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
  - "C4183"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4183"
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4183
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : type de retour manquant ; fonction membre retournant 'int' prise par défaut  
  
 La définition en ligne d'une fonction membre dans une classe ou une structure n'a pas de type de retour.  Cette fonction membre est supposée avoir un type de retour par défaut `int`.  
  
 L'exemple suivant génère l'erreur C4183 :  
  
```  
// C4183.cpp  
// compile with: /W1 /c  
#pragma warning(disable : 4430)  
class MyClass1;  
class MyClass2 {  
   MyClass1() {};   // C4183  
};  
```