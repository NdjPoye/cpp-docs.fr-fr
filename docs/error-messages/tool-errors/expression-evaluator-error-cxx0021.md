---
title: "&#201;valuateur d&#39;expression, erreur CXX0021 | Microsoft Docs"
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
  - "CXX0021"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0021"
  - "CXX0021"
ms.assetid: d6c0c35a-16c2-42c0-a7d2-e910350a47f0
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &#201;valuateur d&#39;expression, erreur CXX0021
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

struct ou union utilisé comme scalaire  
  
 Une structure ou une union est utilisée dans une expression, mais aucun élément n'est spécifié.  
  
 Lors de la manipulation d'une variable de structure ou d'union, le nom de la variable peut apparaître seul, sans qualificateur de champ.  Si une structure ou une union est utilisée dans une expression, elle doit être qualifiée par l'élément précis voulu.  
  
 Spécifiez l'élément dont la valeur doit être utilisée dans l'expression.  
  
 Erreur identique à CAN0021.