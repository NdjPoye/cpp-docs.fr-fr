---
title: "Ligne de commande DUMPBIN | Microsoft Docs"
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
  - "dumpbin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "programme DUMPBIN, ligne de commande"
ms.assetid: e6ad17d3-965d-41aa-9dfd-75bb073718d4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ligne de commande DUMPBIN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour exécuter DUMPBIN, utilisez la syntaxe suivante :  
  
```  
DUMPBIN [options] files...  
```  
  
 Spécifiez un ou plusieurs fichiers binaires ainsi que les options requises pour déterminer les informations voulues.  DUMPBIN envoie les informations vers une sortie standard.  Vous pouvez rediriger ces informations vers un fichier ou utiliser l'option \/OUT afin de spécifier un nom de fichier pour la sortie.  
  
 Lorsque vous exécutez DUMPBIN sur un fichier sans spécifier d'option, DUMPBIN affiche la sortie \/SUMMARY.  
  
 Lorsque vous tapez uniquement la commande `dumpbin` sur la ligne de commande, DUMPBIN affiche une instruction d'utilisation qui récapitule ses options.  
  
## Voir aussi  
 [Outils de génération C\/C\+\+](../../build/reference/c-cpp-build-tools.md)   
 [Référence DUMPBIN](../../build/reference/dumpbin-reference.md)