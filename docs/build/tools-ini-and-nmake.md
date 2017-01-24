---
title: "Tools.ini et NMAKE | Microsoft Docs"
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
  - "programme NMAKE, lire des fichiers"
  - "Tools.ini et NMake"
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Tools.ini et NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE lit Tools.ini avant de lire les makefiles, sauf quand l'option \/R est utilisée.  Il recherche Tools.ini d'abord dans le répertoire en cours puis dans le répertoire indiqué par la variable d'environnement INIT.  Dans le fichier d'initialisation, la section des paramètres NMAKE commence par `[NMAKE]` et peut contenir des informations concernant n'importe quel makefile.  Placez un commentaire ou une ligne séparée commençant par le signe dièse \(\#\).  
  
## Voir aussi  
 [Exécution de NMAKE](../build/running-nmake.md)