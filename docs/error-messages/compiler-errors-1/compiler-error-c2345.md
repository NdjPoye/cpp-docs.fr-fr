---
title: "Erreur du compilateur C2345 | Microsoft Docs"
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
  - "C2345"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2345"
ms.assetid: e1cc88b0-0223-4d07-975b-fa99956a82bd
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2345
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

align\(valeur\) : valeur d’alignement non conforme  
  
 Vous avez passé une valeur au mot clé [align](../../cpp/align-cpp.md) qui n’est pas comprise dans la plage autorisée.  
  
 L’exemple suivant génère l’erreur C2345 :  
  
```  
// C2345.cpp // compile with: /c __declspec(align(0)) int a;   // C2345 __declspec(align(1)) int a;   // OK  
```