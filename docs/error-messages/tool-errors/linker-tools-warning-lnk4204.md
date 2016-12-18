---
title: "Avertissement des outils &#201;diteur de liens LNK4204 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4204"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4204"
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4204
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'NomFichier' n'a pas d'informations de débogage pour référencer le module ; édition de liens des objets comme s'il n'y avait aucune information de débogage  
  
 Le fichier .pdb a une signature erronée.  L'éditeur de liens poursuit la liaison de l'objet sans les informations de débogage.  Vous pouvez essayer de recompiler le fichier objet avec l'option [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
 LNK4204 peut se produire si certains objets de la bibliothèque font référence à un fichier qui n'existe plus.  Cela peut arriver lors de la régénération de la solution, par exemple ; un fichier objet peut avoir été supprimé et ne pas être régénéré à cause d'une erreur de compilation.  Dans ce cas, compilez avec **\/Z7** ou avec **\/Fd** pour mettre à jour les objets afin qu'ils fassent référence à un fichier unique par bibliothèque \(il ne s'agit pas du nom de fichier .pdb par défaut\).  Pour plus d'informations, consultez [\/Fd \(Nom de fichier PDB\)](../../build/reference/fd-program-database-file-name.md).  Vérifiez que le fichier .pdb est enregistré avec la bibliothèque chaque fois qu'elle est mise à jour dans le système de contrôle de code source.