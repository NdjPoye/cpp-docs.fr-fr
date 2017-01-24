---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0030 | Microsoft Docs"
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
  - "PRJ0030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0030"
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur de g&#233;n&#233;ration de projet PRJ0030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erreur d'expansion macro.La récurrence d'évaluation a dépassé 32 niveaux pour $\(macro\).  
  
 Cette erreur est provoquée par la récurrence dans vos macros.  Par exemple, si vous affectez la valeur $\(IntDir\) à la propriété **Répertoire intermédiaire** \(consultez [Général, Page de propriétés \(Projet\)](../../ide/general-property-page-project.md)\), la récurrence se produit.  
  
 Pour corriger cette erreur, ne définissez pas les macros ou les propriétés comme des macros qui sont utilisées pour définir.