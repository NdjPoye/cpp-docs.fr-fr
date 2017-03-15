---
title: "Erreur du compilateur C3413 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3413"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3413"
ms.assetid: de6c9b05-c373-4bd8-8cb0-12c2cd2e5674
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3413
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'nom' : instanciation explicite non valide  
  
 Le compilateur a détecté une instanciation explicite incorrecte.  
  
 L’exemple suivant génère l’erreur C3413 :  
  
```  
// C3413.cpp template class MyClass {};   // C3413  
```  
  
 Solution possible :  
  
```  
// C3413b.cpp // compile with: /c template <class T> class MyClass {}; template <> class MyClass<int> {};  
```