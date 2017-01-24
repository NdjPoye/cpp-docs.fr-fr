---
title: "Erreur irr&#233;cup&#233;rable NMAKE U1051 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1051"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1051"
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable NMAKE U1051
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

mémoire insuffisante  
  
 NMAKE ne dispose plus d'une quantité de mémoire suffisante, y compris la mémoire virtuelle, car le makefile est trop volumineux ou complexe.  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Libérez de l'espace sur le disque.  
  
2.  Augmentez la taille du fichier de pagination sous Windows NT ou d'échange sous Windows.  
  
3.  Si une partie seulement du makefile est utilisée, divisez le makefile en plusieurs fichiers ou utilisez les directives de prétraitement **\!IF** pour limiter la quantité que NMAKE doit traiter.  Les directives **\!IF** sont les suivantes : **\!IF**, `!IFDEF`, **\!IFNDEF**, **\!ELSE IF**, **\!ELSE** `IFDEF` et **\!ELSE** `IFNDEF`.