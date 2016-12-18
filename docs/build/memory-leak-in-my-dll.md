---
title: "Il y a une fuite de m&#233;moire dans ma DLL r&#233;guli&#232;re, pourtant le code semble correct. Comment trouver cette fuite de m&#233;moire&#160;? | Microsoft Docs"
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
  - "DLL (C++), fuites de mémoire"
  - "fuites de mémoire (C++), DLL"
ms.assetid: a5d76573-b567-4b6a-8303-dafeeed9204d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Il y a une fuite de m&#233;moire dans ma DLL r&#233;guli&#232;re, pourtant le code semble correct. Comment trouver cette fuite de m&#233;moire&#160;?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La fuite de mémoire peut avoir comme cause possible la création par la bibliothèque MFC d'objets temporaires qui sont utilisés dans des fonctions gestionnaires de messages.  Dans les DLL normales, la bibliothèque MFC ne libère pas automatiquement la mémoire allouée pour ces objets.  Pour plus d'informations, consultez [Gestion de la mémoire et tas de débogage](http://msdn.microsoft.com/fr-fr/34dc6ef6-31c9-460e-a2a7-15e7f8e3334b) ou l'article de la Base de connaissances \(en anglais\) « Cleaning Up Temporary MFC Objects in \_USRDLL DLLs » \(Q105286\).  
  
 Remarquez que le terme USRDLL n'a plus cours dans la documentation Visual C\+\+.  Une DLL normale liée de manière statique aux MFC possède les mêmes caractéristiques que l'ancienne USRDLL.  Les conseils de l'article de la Base de connaissances s'appliquent également aux DLL normales liées de manière dynamique aux MFC.  Les informations fournies par l'article de la Base de connaissances ci\-dessus s'appliquent à la fois aux DLL normales liées de manière statique aux MFC et aux DLL normales liées de manière dynamique aux MFC.  
  
## Voir aussi  
 [Forum Aux Questions à propos des DLL](../build/dll-frequently-asked-questions.md)