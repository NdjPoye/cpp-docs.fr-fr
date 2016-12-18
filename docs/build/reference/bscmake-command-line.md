---
title: "Ligne de commande BSCMAKE | Microsoft Docs"
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
  - "BSCMAKE, ligne de commande"
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ligne de commande BSCMAKE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour exécuter BSCMAKE à partir de la ligne de commande, utilisez la syntaxe suivante :  
  
```  
BSCMAKE [options] sbrfiles  
```  
  
 Les options ne peuvent apparaître que dans le champ `options` de la ligne de commande.  
  
 Le champ *sbrfiles* spécifie un ou plusieurs fichiers .sbr créés par un compilateur ou un assembleur.  Séparez les noms des fichiers .sbr par des espaces ou des tabulations.  Vous devez spécifier l'extension ; elle n'est pas ajoutée par défaut.  Vous pouvez indiquer un chemin d'accès et un nom de fichier ou utiliser les caractères génériques du système d'exploitation \(\* et ?\).  
  
 Au cours d'une génération incrémentielle, vous pouvez spécifier de nouveaux fichiers .sbr qui ne participaient pas à la génération d'origine.  Si vous souhaitez que le fichier d'informations de consultation conserve toutes les contributions, vous devez spécifier tous les fichiers .sbr \(même tronqués\) qui ont servi à la création du fichier .bsc d'origine.  Si vous omettez un fichier .sbr, il ne contribue pas à la génération du fichier d'informations de consultation.  
  
 Ne spécifiez pas de fichier .sbr tronqué pour une génération complète.  Ce type de génération nécessite la contribution de tous les fichiers .sbr spécifiés.  Avant d'effectuer une génération complète, recompilez le projet et créez un nouveau fichier .sbr pour chaque fichier vide.  
  
 La commande suivante exécute BSCMAKE pour créer un fichier nommé MAIN.bsc à partir de trois fichiers .sbr :  
  
```  
BSCMAKE main.sbr file1.sbr file2.sbr  
```  
  
 Pour plus d'informations, consultez [BSCMAKE, fichier de commandes](../../build/reference/bscmake-command-file-response-file.md) et [BSCMAKE, options](../../build/reference/bscmake-options.md).  
  
## Voir aussi  
 [Référence BSCMAKE](../../build/reference/bscmake-reference.md)