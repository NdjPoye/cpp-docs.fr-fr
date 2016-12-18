---
title: "Erreur irr&#233;cup&#233;rable NMAKE U1099 | Microsoft Docs"
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
  - "U1099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1099"
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable NMAKE U1099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

dépassement de capacité de la pile  
  
 Le makefile en cours de traitement était trop complexe pour la taille de la pile dans NMAKE.  NMAKE a une allocation de 0x3000 \(12 Ko\)  
  
 Pour augmenter l'allocation de pile de NMAKE, exécutez l'utilitaire [editbin \/stack](../../build/reference/stack.md) avec une option de pile plus importante :  
  
 **editbin \/STACK:reserve NMAKE.EXE**  
  
 où *réserve* est un nombre supérieur à l'allocation de piles en cours dans NMAKE.