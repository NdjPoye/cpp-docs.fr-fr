---
title: "Erreur du compilateur C3297 | Microsoft Docs"
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
  - "C3297"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3297"
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3297
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'constraint\_2' : impossible d’utiliser 'constraint\_1' en tant que contrainte, car 'constraint\_1' a la contrainte de valeur  
  
 Les classes de valeur sont sealed. Si une contrainte est une classe de valeur, une autre contrainte ne peut jamais dériver de celle\-ci.  
  
 Pour plus d'informations, consultez [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3297 :  
  
```  
// C3297.cpp // compile with: /clr /c generic<class T, class U> where T : value class where U : T   // C3297 public ref struct R {};  
```