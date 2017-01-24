---
title: "Avertissement du compilateur (niveau&#160;3) C4023 | Microsoft Docs"
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
  - "C4023"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4023"
ms.assetid: 615d5374-d7c1-42eb-acfd-917c053270c8
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;3) C4023
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : pointeur based passé à une fonction non prototypée : paramètre nombre  
  
 Passer un pointeur based à une fonction non prototypée entraîne la normalisation du pointeur, avec des résultats imprévisibles.  
  
 Vous pouvez résoudre cet avertissement en utilisant des fonctions prototypées auxquelles sont passées des pointeurs based.