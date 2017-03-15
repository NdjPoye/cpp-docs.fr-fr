---
title: "Avertissement du compilateur (niveau 1) C4651 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4651"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4651"
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4651
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'définition' spécifiée pour l'en\-tête précompilé mais non pour la compilation active  
  
 La définition a été spécifiée lorsque l'en\-tête précompilé a été généré, mais pas dans cette compilation.  
  
 La définition sera appliquée à l'intérieur de l'en\-tête précompilé, mais pas dans le reste du code.  
  
 Lorsqu'un en\-tête précompilé a été généré avec \/DSYMBOL, le compilateur générera cet avertissement si la compilation \/Yu ne comprend pas \/DSYMBOL.  L'ajout de \/DSYMBOL à la ligne de commande \/Yu résout cet avertissement.