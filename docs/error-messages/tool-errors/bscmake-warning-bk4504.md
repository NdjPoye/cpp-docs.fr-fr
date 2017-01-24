---
title: "Avertissement BSCMAKE BK4504 | Microsoft Docs"
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
  - "BK4504"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK4504"
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement BSCMAKE BK4504
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le fichier contient trop de références ; les références ultérieures provenant de cette source seront ignorées  
  
 Le fichier .cpp contient plus de 64.000 références de symbole.  Lorsque BSCMAKE a rencontré 64.000 références dans un fichier, il ignore toutes les références ultérieures.  
  
 Pour corriger ce problème, sectionnez le fichier en deux fichiers ou plus, chacun possédant moins de 64.000 références de symbole, ou utilisez la directive du préprocesseur `#pragma component(browser)` pour limiter les symboles générés pour les références spécifiques.  Pour plus d'informations, consultez [composant](../../preprocessor/component.md).