---
title: "Chemins de recherche des d&#233;pendants | Microsoft Docs"
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
  - "dépendants, NMAKE"
  - "programme NMAKE, dépendants"
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Chemins de recherche des d&#233;pendants
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

À chaque dépendant correspond un chemin de recherche facultatif, comme indiqué ci\-dessus :  
  
## Syntaxe  
  
```  
{directory[;directory...]}dependent  
```  
  
## Remarques  
 NMAKE commence par rechercher le dépendant dans le répertoire en cours avant d'aborder la recherche parmi les autres répertoires dans l'ordre indiqué.  Une macro peut spécifier tout ou partie d'un chemin de recherche.  Mettez les noms des répertoires entre accolades \({ }\) ; séparez les nombreux répertoires par un point\-virgule \(;\).  Les espaces et les tabulations ne sont pas admis.  
  
## Voir aussi  
 [Dépendants](../build/dependents.md)