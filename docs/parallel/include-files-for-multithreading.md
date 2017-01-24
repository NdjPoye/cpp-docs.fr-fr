---
title: "Fichiers include pour le multithreading | Microsoft Docs"
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
  - "fichiers Include, multithreading"
  - "multithreading (C++), fichiers Include"
  - "threads (C++), fichiers Include"
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fichiers include pour le multithreading
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fichiers Include standard déclarent les fonctions de bibliothèques Runtime C au fur et à mesure que celles\-ci sont implémentées dans les bibliothèques.  Si vous utilisez l'option [Optimisation complète](../build/reference/ox-full-optimization.md) \(\/Ox\) ou [convention d'appel fastcall](../build/reference/gd-gr-gv-gz-calling-convention.md) \(\/Gr\), le compilateur suppose que toutes les fonctions doivent être appelées à l'aide de la convention d'appel des registres.  Les fonctions des bibliothèques Runtime sont compilées à l'aide de la convention d'appel du C, et les déclarations dans les fichiers Include standard indiquent au compilateur de générer des références externes correctes vers ces fonctions.  
  
## Voir aussi  
 [Multithreading à l'aide de C et de Win32](../parallel/multithreading-with-c-and-win32.md)