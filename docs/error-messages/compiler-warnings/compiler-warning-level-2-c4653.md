---
title: "Avertissement du compilateur (niveau 2) C4653 | Microsoft Docs"
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
  - "C4653"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4653"
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 2) C4653
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

option du compilateur 'option' non cohérente avec l'en\-tête précompilé ; option active de ligne de commande ignorée  
  
 Une option spécifiée avec l'option Utiliser un en\-tête précompilé \([\/Yu](../../build/reference/yu-use-precompiled-header-file.md)\) n'était pas cohérente avec les options spécifiées lors de la création de l'en\-tête précompilé.  Cette compilation a utilisé l'option spécifiée lors de la création de l'en\-tête précompilé.  
  
 Cet avertissement peut se produire lorsqu'une valeur différente de l'option Pack Structures \([\/Zp](../../build/reference/zp-struct-member-alignment.md)\) a été spécifiée pendant la compilation de l'en\-tête précompilé.