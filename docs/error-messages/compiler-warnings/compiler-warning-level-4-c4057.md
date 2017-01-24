---
title: "Avertissement du compilateur (niveau&#160;4) C4057 | Microsoft Docs"
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
  - "C4057"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4057"
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4057
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : 'identificateur1' diffère de 'identificateur2' dans l’indirection vers des types de base légèrement différents  
  
 Deux expressions de pointeur font référence à des types de base différents. Les expressions sont utilisées sans conversion.  
  
### Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Mélange de types signés et non signés.  
  
2.  Mélange de types **short** et **long**.