---
title: "Manipulateurs de flux d&#39;entr&#233;e | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "objets de flux d'entrée"
  - "flux d'entrée, manipulateurs"
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Manipulateurs de flux d&#39;entr&#233;e
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

De nombreux manipulateurs, tels que [setprecision](../Topic/setprecision.md), sont définis pour la classe `ios` et s'appliquent ainsi aux flux d'entrée.  Nombre de manipulateurs, toutefois, affectent les objets de flux d'entrée.  Parmi ceux ci, les plus importants sont les manipulateurs de base, `dec`, `oct`, et `hex`, qui déterminent la base de conversion utilisée avec des nombres du flux d'entrée.  
  
 Sur l'extraction, le manipulateur `hex` permet le traitement de plusieurs formats d'entrée.  Par exemple, c, c c, 0xc, 0xC, 0Xc, et 0XC tous sont interprétés comme l'entier décimal 12.  Tout caractère autre que 0 à 9, de A à F, à un à f, à x, et X termine la conversion numérique.  Ainsi la séquence `"124n5"` est convertie au nombre 124 le bit [basic\_ios::fail](../Topic/basic_ios::fail.md) défini.  
  
## Voir aussi  
 [Flux d'entrée](../standard-library/input-streams.md)