---
title: "&#201;valuateur d&#39;expression, erreur CXX0039 | Microsoft Docs"
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
  - "CXX0039"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0039"
  - "CXX0039"
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &#201;valuateur d&#39;expression, erreur CXX0039
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

symbole ambigu  
  
 L'évaluateur d'expression C ne peut pas déterminer quelle instance d'un symbole il doit utiliser dans une expression.  Le symbole apparaît plusieurs fois dans l'arborescence d'héritage.  
  
 Vous devez utiliser l'opérateur de résolution de portée \(`::`\) pour spécifier de manière explicite l'instance à utiliser dans l'expression.  
  
 Erreur identique à CAN0039.