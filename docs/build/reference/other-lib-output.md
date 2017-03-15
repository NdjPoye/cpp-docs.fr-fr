---
title: "Autre sortie LIB | Microsoft Docs"
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
ms.assetid: 656864a6-0b7a-4633-8dc6-ee3b1766d836
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Autre sortie LIB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dans le mode par défaut, vous pouvez utiliser l'option \/LIST pour afficher des informations relatives à la bibliothèque résultante.  Vous pouvez rediriger cette sortie vers un fichier.  
  
 LIB affiche un message de copyright et un numéro de version, et reproduit en écho les fichiers de commandes quand l'option \/NOLOGO n'est pas utilisée.  
  
 Lorsque vous tapez uniquement `lib`, LIB affiche une instruction d'utilisation récapitulant ses options.  
  
 Les messages d'erreur et d'avertissement émis par LIB ont le format LNK*nnnn*.  Les outils LINK, DUMPBIN et EDITBIN utilisent également cette plage d'erreurs.  Pour accéder à l'aide, il suffit de sélectionner l'erreur dans la fenêtre sortie et d'appuyer sur la touche F1.  
  
## Voir aussi  
 [Vue d'ensemble de LIB](../../build/reference/overview-of-lib.md)