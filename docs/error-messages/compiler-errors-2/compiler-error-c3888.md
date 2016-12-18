---
title: "Erreur du compilateur C3888 | Microsoft Docs"
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
  - "C3888"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3888"
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3888
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name' : l’expression const associée à cette donnée membre littérale n’est pas prise en charge par C\+\+\/CLI  
  
 La donnée membre *nom* déclarée avec le mot clé [literal](../../windows/literal-cpp-component-extensions.md) est initialisée avec une valeur qui n’est pas prise en charge par le compilateur. Le compilateur prend en charge uniquement les types constant, integral, enum et string. Il est probable que l’erreur **C3888** soit causée par l’utilisation d’un tableau d’octets pour l’initialisation de la donnée membre.  
  
### Pour corriger cette erreur  
  
1.  Vérifiez que le type de la donnée membre littérale déclarée est pris en charge.  
  
## Voir aussi  
 [literal](../../windows/literal-cpp-component-extensions.md)