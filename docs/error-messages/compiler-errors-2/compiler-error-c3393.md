---
title: "Erreur du compilateur C3393 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3393"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3393"
ms.assetid: d57f7c69-0a02-4fe3-9e45-bc62644fd77c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3393
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de syntaxe dans la clause de contrainte : 'identificateur' n’est pas un type  
  
 L’identificateur passé à une contrainte, qui doit être un type, n’était pas un type.  Pour plus d'informations, consultez [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3393 :  
  
```  
// C3393.cpp // compile with: /clr /c void MyInterface() {} interface class MyInterface2 {}; generic<typename T> where T : MyInterface   // C3393 // try the following line instead // where T : MyInterface2 ref class R {};  
```