---
title: "Erreur irr&#233;cup&#233;rable C1091 | Microsoft Docs"
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
  - "C1091"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1091"
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1091
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Limite du compilateur : la longueur de la chaîne dépasse de 'longueur' octets  
  
 Une constante de chaîne a dépassé la limite actuelle de longueur de chaîne.  
  
 Fractionnez la chaîne statique en deux variables \(ou davantage\) et utilisez [strcpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) pour joindre le résultat dans le cadre de la déclaration ou au moment de l’exécution.