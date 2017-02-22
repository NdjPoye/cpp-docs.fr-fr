---
title: "Erreur du compilateur C2801 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2801"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2801"
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2801
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator opérateur' doit être un membre non static  
  
 Les opérateurs suivants ne peuvent être surchargés qu'en tant que membres non statiques :  
  
-   Assignation `=`  
  
-   Accès au membre de classe `->`  
  
-   Mettre en indice `[]`  
  
-   Appel de fonction `()`  
  
 Causes possibles de l'erreur C2801 :  
  
-   L'opérateur surchargé n'est pas membre d'une classe, d'une structure ou d'une union.  
  
-   L'opérateur surchargé est déclaré comme `static`.  
  
-   L'exemple suivant génère l'erreur C2801 :  
  
```  
// C2801.cpp  
// compile with: /c  
operator[]();   // C2801 not a member  
class A {  
   static operator->();   // C2801 static  
   operator()();   // OK  
};  
```