---
title: "Inclusion des noms de fichier entre crochets | Microsoft Docs"
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
  - "C"
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Inclusion des noms de fichier entre crochets
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.8.2** Méthode utilisée pour localiser les fichiers à inclure  
  
 Pour les caractéristiques du fichier placées entre crochets pointus, le préprocesseur n'effectue pas de recherche dans les répertoires des fichiers parents.  Le fichier « parent » est le fichier qui contient la directive [\#include](../preprocessor/hash-include-directive-c-cpp.md).  Au lieu de cela, il commence par rechercher le fichier dans les répertoires spécifiés sur la ligne de commande du compilateur située après \/I.  Si l'option \/I est absente ou échoue, le préprocesseur utilise la variable d'environnement INCLUDE pour rechercher tous les fichiers Include entre crochets pointus.  La variable d'environnement INCLUDE peut contenir plusieurs chemins séparés par des points\-virgules \(**;**\).  Si plusieurs répertoires figurent dans l'option \/I ou la variable d'environnement INCLUDE, le préprocesseur les traite dans l'ordre dans lequel ils apparaissent.  
  
## Voir aussi  
 [Directives de prétraitement](../c-language/preprocessing-directives.md)