---
title: "Erreur irr&#233;cup&#233;rable C1026 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1026"
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur irr&#233;cup&#233;rable C1026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

dépassement de capacité de la pile de l'analyseur, programme trop complexe  
  
 L'espace requis pour analyser le programme a causé un dépassement de capacité de la pile du compilateur.  
  
 Diminuez la complexité des expressions en :  
  
-   Diminuant le niveau d'imbrication des instructions `for` et `switch`.  Placez les instructions les plus fortement imbriquées dans des fonctions séparées.  
  
-   Divisant les expressions longues faisant appel à des opérateurs à virgule ou des appels de fonction.