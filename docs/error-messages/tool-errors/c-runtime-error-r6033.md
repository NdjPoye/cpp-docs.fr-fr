---
title: "Erreur d’ex&#233;cution de C R6033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6033"
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Erreur d&#39;ex&#233;cution C R6033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Tentative d'utilisation du code MSIL de cet assembly pendant l'initialisation du code natif.Cette erreur indique la présence d'une bogue dans votre application.Elle est très probablement le résultat de l'appel d'une fonction compilée par MSIL \(\/clr\) provenant d'un constructeur natif ou de DIIMain.  
  
 Ce diagnostic indique que les instructions MSIL s'exécutaient lors du verrouillage du chargeur.  Pour plus d'informations, consultez [Initialisation d'assemblys mixtes](../../dotnet/initialization-of-mixed-assemblies.md).