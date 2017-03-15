---
title: "Ordre des options CL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compilateur cl.exe, définir des options"
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ordre des options CL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les options peuvent figurer n'importe où sur la ligne de commande CL, sauf l'option \/link, qui doit figurer en dernier.  Le compilateur commence par les options spécifiées dans la [variable d'environnement CL](../../build/reference/cl-environment-variables.md), puis lit la ligne de commande de gauche à droite, en traitant les fichiers de commandes dans l'ordre où il les trouve.  Chaque option s'applique à tous les fichiers indiqués sur la ligne de commande.  Si CL rencontre des options en conflit, elle utilise l'option la plus à droite.  
  
## Voir aussi  
 [Syntaxe de la ligne de commande du compilateur](../../build/reference/compiler-command-line-syntax.md)