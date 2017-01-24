---
title: "Comment&#160;: tester l&#39;&#233;galit&#233; (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "égalité, test de"
ms.assetid: 9115e298-9f75-452d-bdfb-6eeb0fa0b3c6
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: tester l&#39;&#233;galit&#233; (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans l'exemple suivant, un test d'égalité qui utilise les extensions managées pour C\+\+ est basé sur les éléments auxquels les handles font référence.  
  
## Exemple  
  
```  
// mcppv2_equality_test.cpp  
// compile with: /clr /LD  
using namespace System;  
  
bool Test1() {  
   String ^ str1 = "test";  
   String ^ str2 = "test";  
   return (str1 == str2);  
}  
```  
  
 L'IL \(Intermediate Language\) de ce programme indique que la valeur de retour est implémentée à l'aide d'un appel à op\_Equality.  
  
```  
IL_0012:  call       bool [mscorlib]System.String::op_Equality(string,  
                                                               string)  
```  
  
## Voir aussi  
 [Types managés](../dotnet/managed-types-cpp-cli.md)