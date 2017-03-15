---
title: "Utilisation de biblioth&#232;ques d&#39;importation et de fichiers d&#39;exportation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exporter des fichiers"
  - "bibliothèques d'importation"
  - "bibliothèques d'importation, créer"
  - "LIB (C++), /DEF (option)"
  - "LIB (C++), bibliothèques d'importation et fichiers d'exportation"
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Utilisation de biblioth&#232;ques d&#39;importation et de fichiers d&#39;exportation
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser LIB avec l'option \/DEF pour créer une bibliothèque d'importation et un fichier d'exportation.  LINK utilise le fichier d'exportation pour générer un programme contenant des exportations \(généralement une DLL\) et utilise la bibliothèque d'importation pour résoudre les références à ces exportations dans d'autres programmes.  
  
 Notez que si vous créez votre bibliothèque d'importation lors d'une étape préliminaire, avant de créer votre fichier .dll, vous devez passer lors de la génération du fichier .dll le même jeu de fichiers objets que celui que vous avez passé lors de la génération de la bibliothèque d'importation.  
  
 Dans la plupart des cas, vous n'avez pas besoin de recourir à LIB pour créer la bibliothèque d'importation.  Lorsque vous liez un programme \(un fichier exécutable ou une DLL\) qui contient des exportations, LINK crée automatiquement une bibliothèque d'importation décrivant les exportations.  Par la suite, lorsque vous liez un programme qui référence ces exportations, vous spécifiez la bibliothèque d'importation.  
  
 Cependant, quand une DLL exporte vers un programme à partir duquel elle importe aussi, directement ou indirectement, vous devez utiliser LIB pour créer l'une des bibliothèques d'importation.  Quand LIB crée une bibliothèque d'importation, il crée également un fichier d'exportation.  Vous devez utiliser le fichier d'exportation lors de la liaison de l'une des DLL.  
  
## Voir aussi  
 [Référence LIB](../../build/reference/lib-reference.md)