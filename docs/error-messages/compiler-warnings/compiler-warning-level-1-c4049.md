---
title: "Avertissement du compilateur (niveau 1) C4049 | Microsoft Docs"
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
  - "C4049"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4049"
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

limite du compilateur : arrêt de l'émission du numéro de ligne  
  
 Le fichier contient plus de 16 777 215 \(2<sup>24</sup>\-1\) lignes sources.  Le compilateur arrête la numérotation à 16 777 215.  
  
 Pour le code situé après la ligne 16 777 215 :  
  
-   L'image ne contiendra aucune information de débogage pour les numéros de ligne.  
  
-   Certains diagnostics peuvent être signalés avec des numéros de ligne incorrects.  
  
-   Les listes .asm \(\/FAs\) peuvent posséder des numéros de ligne incorects.