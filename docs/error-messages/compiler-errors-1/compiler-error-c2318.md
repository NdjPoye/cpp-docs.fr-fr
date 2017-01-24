---
title: "Erreur du compilateur C2318 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2318"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2318"
ms.assetid: 169e30b9-df78-46cb-90bf-576ad3c32fd4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2318
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

aucun bloc try associé à ce gestionnaire catch  
  
 Un gestionnaire `catch` est défini, mais il n’est pas précédé d’un bloc `try`.  
  
 L’exemple suivant génère l’erreur C2318 :  
  
```  
// C2318.cpp // compile with: /EHsc #include <eh.h> int main() { // no try block catch( int ) {}   // C2318 }  
```  
  
 Solution possible :  
  
```  
// C2318b.cpp // compile with: /EHsc #include <eh.h> int main() { try{} catch( int ) {} }  
```