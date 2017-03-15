---
title: "Compiler Error C3550 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3550"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3550"
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compiler Error C3550
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'decltype\(auto\)' simple est le seul autorisé dans ce contexte  
  
 Si `decltype(auto)` est utilisé comme espace réservé pour le type de retour d'une fonction, il doit être utilisé par lui\-même.  Il ne peut pas être utilisé dans le cadre d'une déclaration de pointeur \(`decltype(auto*)`\), d'une déclaration de référence \(`decltype(auto&)`\) ni de toute autre qualification de ce genre.  
  
## Voir aussi  
 [auto](../../cpp/auto-cpp.md)