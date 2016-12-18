---
title: "Pseudocibles | Microsoft Docs"
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
  - "makefiles, pseudocibles"
  - "programme NMAKE, pseudocibles"
  - "programme NMAKE, cibles"
  - "pseudocibles et NMAKE"
  - "horodatage, pseudocibles de makefile"
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Pseudocibles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une pseudocible est une étiquette utilisée à la place d'un nom de fichier dans une ligne de dépendance.  Elle est interprétée en tant que fichier inexistant et est par conséquent obsolète.  NMAKE suppose que l'horodatage d'une pseudocible est le plus récent de tous ses dépendants.  À défaut de dépendant, c'est l'heure courante qui est utilisée.  Si une pseudocible est utilisée en tant que cible, ses commandes sont toujours exécutées.  Une pseudocible utilisée comme dépendant doit également apparaître en tant que cible dans une autre dépendance.  Cette dépendance n'a, cependant, pas besoin d'avoir un bloc de commandes.  
  
 Les noms des pseudocibles obéissent aux règles de syntaxe des noms de fichiers s'appliquant aux cibles.  Cependant, si le nom ne possède pas d'extension \(autrement dit, s'il ne contient pas de point\), il peut dépasser la limite des 8 caractères pour les noms de fichiers et compter jusqu'à 256 caractères.  
  
## Voir aussi  
 [Cibles](../build/targets.md)