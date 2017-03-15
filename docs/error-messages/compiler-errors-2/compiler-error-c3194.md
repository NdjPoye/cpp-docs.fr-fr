---
title: "Erreur du compilateur C3194 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3194"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3194"
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3194
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : un type valeur ne peut pas avoir d'opérateur d'assignation  
  
 Les fonctions membre spéciales qui exigent un appel automatique par le compilateur, telles qu'un constructeur de copie ou l'opérateur d'assignation de copie, ne sont pas prises en charge dans une classe value.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3194 :  
  
```  
// C3194.cpp  
// compile with: /clr /c  
value struct MyStruct {  
   MyStruct& operator= (const MyStruct& i) { return *this; }   // C3194  
};  
  
ref struct MyStruct2 {  
   MyStruct2% operator= (const MyStruct2% i) { return *this; }   // OK  
};  
```