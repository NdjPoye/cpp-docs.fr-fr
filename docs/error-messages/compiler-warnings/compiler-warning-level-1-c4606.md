---
title: "Avertissement du compilateur (niveau 1) C4606 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4606"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4606"
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4606
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma warning : 'numéro\_avertissement' ignoré ; les avertissements liés à l'analyse du code ne sont pas associés à des niveaux d'avertissement  
  
 Pour les avertissements liés à l'analyse du code, seuls `error`, `once` et `default` sont pris en charge avec le pragma [warning](../../preprocessor/warning.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4606 :  
  
```  
// C4606.cpp  
// compile with: /c /W1  
#pragma warning(1: 6001)   // C4606  
#pragma warning(once: 6001)   // OK  
```