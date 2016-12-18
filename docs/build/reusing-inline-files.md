---
title: "R&#233;utilisation de fichiers inline | Microsoft Docs"
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
  - "fichiers inline, (NMAKE) réutiliser"
  - "programme NMAKE, fichiers inline"
  - "réviser les fichiers inline"
ms.assetid: d42dbffb-2cef-4ccb-9a1f-20b8ef81481c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# R&#233;utilisation de fichiers inline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour réutiliser un fichier inline, spécifiez \<\<*nomfichier* où le fichier est défini et utilisé en premier, puis réutilisez *nomfichier* sans \<\< ultérieurement dans la même commande ou dans une commande différente.  La commande de création du fichier inline doit être exécutée avant toutes les commandes utilisant ce fichier.  
  
## Voir aussi  
 [Fichiers inline dans un makefile](../build/inline-files-in-a-makefile.md)