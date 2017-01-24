---
title: "&#201;valuateur d&#39;expression, erreur CXX0030 | Microsoft Docs"
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
  - "CXX0030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0030"
  - "CXX0030"
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &#201;valuateur d&#39;expression, erreur CXX0030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

expression non évaluée  
  
 L'évaluateur d'expression du débogueur n'a pas pu obtenir de valeur pour l'expression telle qu'elle est rédigée.  L'une des causes probables de cette erreur est que l'expression fait référence à un emplacement mémoire situé hors de l'espace d'adressage du programme \(dans le cas notamment de la suppression de la référence d'un pointeur nul\).  Windows ne permet pas d'accéder aux emplacements mémoire situés hors de l'espace d'adressage du programme.  
  
 Vous pouvez récrire l'expression en utilisant des parenthèses pour contrôler l'ordre d'évaluation.  
  
 Erreur identique à CAN0030.