---
title: "Avertissement du compilateur (niveau 3) C4306 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4306"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4306"
ms.assetid: 5b2192d7-402d-4b6d-8619-08105e7dcac7
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Avertissement du compilateur (niveau 3) C4306
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**'**   
 ***identificateur* ' : la conversion de '**   
 ***type1* ' en '**   
 ***type2* ' d'une taille supérieure**  
  
 L'identificateur subit un cast de type vers un pointeur de type de taille supérieure.  Les bits de poids fort non remplis du nouveau type seront remplis par des zéros.  
  
 Cet avertissement peut indiquer une conversion non désirée.  Le pointeur résultant peut ne pas être valide.