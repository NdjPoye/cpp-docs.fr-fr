---
title: "Avertissement du compilateur (niveau&#160;1) C4025 | Microsoft Docs"
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
  - "C4025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4025"
ms.assetid: c4f6a651-0641-4446-973e-8290065e49ad
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'number' : pointeur based passé à une fonction avec des arguments de variables : paramètre number  
  
 Passer un pointeur based à une fonction avec des arguments de variables entraîne la normalisation du pointeur, avec des résultats imprévisibles. Ne passez pas de pointeurs based à des fonctions avec des arguments de variables.