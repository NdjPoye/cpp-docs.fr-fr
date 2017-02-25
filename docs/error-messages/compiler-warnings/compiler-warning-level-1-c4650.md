---
title: "Avertissement du compilateur (niveau 1) C4650 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4650"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4650"
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4650
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

informations de débogage absentes de l'en\-tête précompilé ; seuls les symboles globaux de l'en\-tête seront disponibles  
  
 Le fichier d'en\-tête précompilé n'a pas été compilé avec l'information de débogage symbolique Microsoft.  
  
 Lorsqu'il est lié, le fichier exécutable ou de bibliothèque de liens dynamiques n'inclura pas les informations de débogage pour les symboles locaux contenus dans l'en\-tête précompilé.  
  
 Vous pouvez éviter cet avertissement en recompilant le fichier d'en\-tête précompilé avec l'option de ligne de commande [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md).