---
title: "Fichiers de sortie LIB | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers de sortie, LIB"
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Fichiers de sortie LIB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les fichiers de sortie produits par LIB dépendent du mode dans lequel celui\-ci est utilisé, comme le montre le tableau suivant.  
  
|Mode|Sortie|  
|----------|------------|  
|Par défaut \(génération ou modification d'une bibliothèque\)|Bibliothèque \(.lib\) COFF|  
|Extraction d'un membre à l'aide de l'option \/EXTRACT|Fichier objet \(.obj\)|  
|Génération d'un fichier d'exportation et d'une bibliothèque d'importation à l'aide de l'option \/DEF|Bibliothèque \(.lib\) d'importation et fichier d'exportation \(.exp\)|  
  
## Voir aussi  
 [Vue d'ensemble de LIB](../../build/reference/overview-of-lib.md)