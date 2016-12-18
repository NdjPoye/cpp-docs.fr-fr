---
title: "Erreur des outils &#201;diteur de liens LNK1241 | Microsoft Docs"
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
  - "LNK1241"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1241"
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1241
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fichier de ressources 'fichier de ressources' déjà spécifié  
  
 Cette erreur est générée si vous lancez manuellement **cvtres** à partir de la ligne de commande puis passez le fichier .obj résultant à l'éditeur de liens en plus d'autres fichiers .res.  
  
 Pour spécifier plusieurs fichiers .res, passez\-les tous à l'éditeur de liens sous forme de fichiers .res, et non depuis des fichiers .obj créés par **cvtres**.