---
title: "&#201;valuateur d&#39;expression, erreur CXX0065 | Microsoft Docs"
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
  - "CXX0065"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0065"
  - "CXX0065"
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &#201;valuateur d&#39;expression, erreur CXX0065
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la variable a besoin du frame de pile  
  
 Une expression contient une variable qui existe dans la portée actuelle mais qui n'a pas encore été créée.  
  
 Cette erreur peut se produire lorsque vous effectuez le pas à pas détaillé du prologue d'une fonction sans avoir configuré le frame de pile de cette fonction, ou encore lorsque vous effectuez le pas à pas détaillé du code de sortie de la fonction.  
  
 Exécutez pas à pas le code du prologue jusqu'à ce que le frame de pile soit configuré avant d'évaluer l'expression.  
  
 Erreur identique à CAN0065.