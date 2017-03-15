---
title: "Erreur des outils &#201;diteur de liens LNK1158 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1158"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1158"
ms.assetid: 45febf16-d9e1-42db-af91-532e2717fd6a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur des outils &#201;diteur de liens LNK1158
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'exécuter 'NomFichier'  
  
 Le fichier exécutable donné appelé par [LINK](../../build/reference/linker-command-line-syntax.md) n'est pas dans le répertoire qui contient LINK ni dans un répertoire spécifié dans la variable d'environnement PATH.  
  
 Vous pouvez par exemple obtenir cette erreur si vous tentez d'utiliser le paramètre PGOPTIMIZE de l'option d'éditeur de liens [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) sur un ordinateur à système d'exploitation 32 bits.