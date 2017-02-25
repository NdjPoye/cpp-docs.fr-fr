---
title: "Avertissement des outils &#201;diteur de liens LNK4001 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4001"
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement des outils &#201;diteur de liens LNK4001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

aucun fichier objet spécifié ; utilisation des bibliothèques  
  
 L'éditeur de liens a passé un ou plusieurs fichiers .lib, mais aucun fichier .obj.  
  
 Comme l'éditeur de liens n'est pas parvenu à accéder aux informations d'un fichier .lib capable d'accéder à un fichier .obj, cet avertissement indique que vous devrez spécifier explicitement d'autres options de l'éditeur de liens.  Par exemple, vous devrez sans doute spécifier les options [\/MACHINE](../../build/reference/machine-specify-target-platform.md), [\/OUT](../../build/reference/out-output-file-name.md) ou [\/ENTRY](../../build/reference/entry-entry-point-symbol.md).