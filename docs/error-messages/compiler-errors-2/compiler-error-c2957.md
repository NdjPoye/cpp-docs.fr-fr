---
title: "Erreur du compilateur C2957 | Microsoft Docs"
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
  - "C2957"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2957"
ms.assetid: 9cb4526f-4af8-47e9-b786-56192627ca72
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2957
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'delim' : délimiteur gauche non valide : '\<' attendu  
  
 Une classe générique était incorrecte.  
  
 L’exemple suivant génère l’erreur C2957 :  
  
```  
// C2957.cpp // compile with: /clr /LD generic << class T>   // C2957 // try the following line instead // generic < class T> gc class C {};  
```