---
title: "Avertissement des outils &#201;diteur de liens LNK4205 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4205"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4205"
ms.assetid: d63b9d18-ef3c-4081-9d8d-93077dad13c2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement des outils &#201;diteur de liens LNK4205
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'NomFichier' n'a pas d'informations de débogage en cours pour référencer le module ; édition de liens des objets comme s'il n'y avait aucune information de débogage  
  
 Le fichier .pdb a des informations obsolètes.  L'éditeur de liens poursuit la liaison de l'objet sans les informations de débogage.  Vous pouvez essayer de recompiler le fichier objet avec l'option [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md).