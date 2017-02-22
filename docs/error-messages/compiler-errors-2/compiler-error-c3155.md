---
title: "Erreur du compilateur C3155 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3155"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3155"
ms.assetid: b04a42e1-64e7-40f8-81fe-c7945348b2cf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3155
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

les attributs ne sont pas autorisés dans un indexeur de propriété  
  
 Une propriété indexée a été déclarée de manière incorrecte.  Pour plus d'informations, consultez [Comment : utiliser des propriétés indexées](../../misc/how-to-use-indexed-properties.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3155 :  
  
```  
// C3155.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct R {  
   property int F[[ParamArray] int] {   // C3155  
   // try the following line instead  
   // property int F[ int] {   // OK  
      int get(int i) {   
         return 0;   
      }  
   }  
};  
```