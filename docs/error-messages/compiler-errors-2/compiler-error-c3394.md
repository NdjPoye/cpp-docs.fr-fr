---
title: "Erreur du compilateur C3394 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3394"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3394"
ms.assetid: 4e025d79-27ba-43c8-b0d9-839ecef98126
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Erreur du compilateur C3394
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de syntaxe dans la clause de contrainte : 'identificateur' trouvé, type attendu  
  
 Une contrainte est incorrecte.  Pour plus d'informations, consultez [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3394 :  
  
```  
// C3394.cpp // compile with: /clr /c ref class MyClass {}; ref class R { generic<typename T> where T : static   // C3394 // try the following line instead // where T : MyClass void f() {} };  
```