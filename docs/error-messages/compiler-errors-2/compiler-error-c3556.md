---
title: "Erreur du compilateur C3556 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3556"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3556"
ms.assetid: 9b002dcc-494e-414f-9587-20c2a0a39333
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3556
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'expression' : argument incorrect pour 'decltype'  
  
 Le compilateur ne peut pas déduire le type de l’expression qui représente l’argument du spécificateur de type `decltype(``expression``)`. Dans l’exemple de code suivant, le compilateur ne peut pas déduire le type de l’argument `myFunction` car `myFunction` est surchargé.  
  
```  
void myFunction(); void myFunction(int); decltype(myFunction); // C3556  
```