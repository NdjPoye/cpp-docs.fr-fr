---
title: "Cibles | Microsoft Docs"
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
  - "cibles, spécifier dans NMAKE"
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Cibles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans une ligne de dépendance, spécifiez une ou plusieurs cibles à l'aide d'un nom de fichier, d'un nom de répertoire ou d'une [pseudocible](../build/pseudotargets.md) valable.  Séparez les cibles multiples par un ou plusieurs espaces ou tabulations.  Les cibles ne respectent pas la casse.  Les chemins d'accès contenant des noms de fichiers sont admis.  Une cible est limitée à 256 caractères.  Si la cible qui précède deux\-points est un caractère unique, utilisez un espace de séparation ; sinon, NMAKE interprète la combinaison lettre\-signe deux\-points comme un spécificateur de lecteur.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
 [Pseudocibles](../build/pseudotargets.md)  
  
 [Cibles multiples](../build/multiple-targets.md)  
  
 [Dépendances cumulatives](../build/cumulative-dependencies.md)  
  
 [Cibles dans des blocs de description multiples](../build/targets-in-multiple-description-blocks.md)  
  
 [Effets secondaires des dépendances](../build/dependency-side-effects.md)  
  
## Voir aussi  
 [Blocs de description](../build/description-blocks.md)