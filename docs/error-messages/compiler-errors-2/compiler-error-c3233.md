---
title: "Erreur du compilateur C3233 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3233"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3233"
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3233
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : paramètre de type générique déjà limité  
  
 Il n’est pas possible de contraindre un paramètre générique dans plusieurs clauses `where`.  
  
 L’exemple suivant génère l’erreur C3233 :  
  
```  
// C3233.cpp // compile with: /clr /LD interface struct C {}; interface struct D {}; generic <class T> where T : C where T : D ref class E {};   // C3233  
```