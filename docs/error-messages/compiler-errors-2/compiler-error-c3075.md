---
title: "Erreur du compilateur C3075 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3075"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3075"
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Erreur du compilateur C3075
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'instance' : vous ne pouvez pas incorporer une instance d’un type référence, 'type', dans un type valeur  
  
 Un type valeur ne peut pas contenir une instance d’un type référence.  
  
 Pour plus d'informations, consultez [Sémantique de pile C\+\+ pour les types de référence](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3075.  
  
```  
// C3075.cpp // compile with: /clr /c ref struct U {}; value struct X { U y;   // C3075 }; ref struct Y { U y;   // OK };  
```