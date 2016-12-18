---
title: "Erreur du compilateur C2524 | Microsoft Docs"
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
  - "C2524"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2524"
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2524
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'destructeur' : un destructeur\/finaliseur doit avoir une liste de paramètres 'void'  
  
 Le destructeur ou finaliseur avait une liste de paramètres de type non [void](../../cpp/void-cpp.md).  Les autres types de paramètres ne sont pas autorisés.  
  
## Exemple  
 Le code suivant reproduit l'erreur C2524.  
  
```  
// C2524.cpp  
// compile with: /c  
class A {  
   A() {}  
   ~A(int i) {}    // C2524  
   // try the following line instead  
   // ~A() {}  
};  
```  
  
## Exemple  
 Le code suivant reproduit l'erreur C2524.  
  
```  
// C2524_b.cpp  
// compile with: /clr /c  
ref struct I1 {  
protected:  
   !I1(int i);   // C2524  
   // try the following line instead  
   // !I1();  
};  
```