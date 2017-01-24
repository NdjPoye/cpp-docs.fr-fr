---
title: "Fichiers .exp en tant qu&#39;entr&#233;e de l&#39;&#201;diteur de liens | Microsoft Docs"
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
  - "fichiers .exp (C++)"
  - "fichiers EXP"
  - "exporter les données, fichiers d'exportation (.exp)"
  - "exporter des fonctions"
  - "exporter des fonctions, informations sur les fonctions exportées"
  - "fonctions (C++), exporter"
  - "bibliothèques d'importation, fichiers de l'éditeur de liens"
  - "liaison (C++), exportations"
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fichiers .exp en tant qu&#39;entr&#233;e de l&#39;&#201;diteur de liens
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les fichiers d'exportation \(.exp\) contiennent des informations sur les fonctions et les éléments de données exportés.  Quand LIB crée une bibliothèque d'importation, il crée également un fichier d'exportation.  Le fichier .exp est utilisé lors de la liaison d'un programme qui exporte ou importe depuis ou vers un autre programme, et ce directement ou indirectement.  Si vous liez un fichier .exp, LINK ne crée pas de bibliothèque d'importation, car il suppose que LIB l'a déjà fait.  Pour plus d'informations sur les fichiers .exp et les bibliothèques d'importation, consultez [Utilisation de bibliothèques d'importation et de fichiers d'exportation](../../build/reference/working-with-import-libraries-and-export-files.md).  
  
## Voir aussi  
 [Fichiers d'entrée LINK](../../build/reference/link-input-files.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)