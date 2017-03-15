---
title: "Avertissement des outils &#201;diteur de liens LNK4105 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4105"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4105"
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement des outils &#201;diteur de liens LNK4105
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

aucun argument spécifié avec l'option 'option'; option ignorée  
  
 Cet avertissement ne survient que quand l'option [\/LIBPATH](../../build/reference/libpath-additional-libpath.md) est définie.  Si aucun répertoire n'est spécifié avec cette option, l'éditeur de liens ignore l'option et génère ce message d'avertissement.  
  
 Si vous n'avez pas besoin de substituer les paramètres d'environnement de bibliothèque, supprimez l'option \/LIBPATH de la ligne de commande de l'éditeur de liens.  Pour utiliser un autre chemin de recherche des bibliothèques, spécifiez cet autre chemin après l'option \/LIBPATH.  
  
## Exemple  
  
```  
link /libpath:c:\filepath\lib bar.obj  
```  
  
 demande à l'éditeur de liens de rechercher les bibliothèques requises dans `c:\filepath\lib` avant de les rechercher dans les emplacements par défaut.