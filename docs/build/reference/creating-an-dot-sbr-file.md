---
title: "Cr&#233;ation d&#39;un fichier .sbr | Microsoft Docs"
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
  - "fichiers .sbr"
  - "BSCMAKE, fichiers d'entrée"
  - "symboles locaux dans les informations de consultation"
  - "fichiers SBR"
  - "fichiers browser sources"
  - "symboles"
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Cr&#233;ation d&#39;un fichier .sbr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les données fournies en entrée à BSCMAKE sont des fichiers .sbr.  Le compilateur crée un fichier .sbr pour chaque fichier objet \(.obj\) compilé.  Lorsque vous générez ou actualisez votre fichier d'informations de consultation, tous les fichiers .sbr du projet doivent être disponibles sur le disque.  
  
 Pour créer un fichier .sbr contenant toutes les informations possibles, spécifiez [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md).  
  
 Pour créer un fichier .sbr qui ne contient aucun symbole local, spécifiez [\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md).  Si les fichiers .sbr contiennent des symboles locaux, vous pouvez néanmoins les omettre dans le fichier .bsc à l'aide de l'[option \/El](../../build/reference/bscmake-options.md)`.` de BSCMAKE.  
  
 Il est possible de créer un fichier .sbr sans effectuer une compilation complète.  Par exemple, spécifiez l'option \/Zs au compilateur pour effectuer une vérification de syntaxe tout en générant un fichier .sbr \(si vous spécifiez également \/FR ou \/Fr\).  
  
 Le processus de génération est parfois plus efficace si les fichiers .sbr sont compressés au préalable pour éliminer les définitions non référencées.  Le compilateur compresse automatiquement les fichiers .sbr.  
  
## Voir aussi  
 [Génération d'un fichier .bsc](../../build/reference/building-a-dot-bsc-file.md)