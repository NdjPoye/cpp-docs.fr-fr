---
title: "Erreur du compilateur C3384 | Microsoft Docs"
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
  - "C3384"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3384"
ms.assetid: c9f92c6a-62a9-4333-b2b1-bc55c7f288b6
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3384
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type\_parameter' : la contrainte de valeur et la contrainte ref s’excluent mutuellement  
  
 Vous ne pouvez pas contraindre un type générique à `value class` et `ref class` à la fois.  
  
 Pour plus d’informations, consultez [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3384.  
  
```  
// C3384.cpp // compile with: /c /clr generic <typename T> where T : ref class where T : value class   // C3384 ref class List {};  
```