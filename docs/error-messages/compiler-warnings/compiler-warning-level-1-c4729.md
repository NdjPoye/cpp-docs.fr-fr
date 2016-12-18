---
title: "Avertissement du compilateur (niveau&#160;1) C4729 | Microsoft Docs"
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
  - "C4729"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4729"
ms.assetid: 36a0151f-f258-48d9-9444-ae6d41ff70a4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4729
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fonction trop importante pour les avertissements bas‚s sur les graphes de flux  
  
 Cet avertissement est généré quand une fonction est trop grande pour être compilée avec un contrôle fiable des situations qui génèrent un avertissement. Cet avertissement n’est généré que quand l’option du compilateur [\/Od](../../build/reference/od-disable-debug.md) est utilisée.  
  
 Pour remédier à cet avertissement, fractionnez la fonction en fonctions plus petites.