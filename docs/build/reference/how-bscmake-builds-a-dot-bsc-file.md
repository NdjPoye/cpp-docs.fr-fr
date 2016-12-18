---
title: "G&#233;n&#233;ration d&#39;un fichier .bsc par BSCMAKE | Microsoft Docs"
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
  - "fichiers d'informations de consultation (.bsc), générer"
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# G&#233;n&#233;ration d&#39;un fichier .bsc par BSCMAKE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

BSCMAKE génère \(ou régénère\) un fichier .bsc de la manière la plus efficace possible.  Pour éviter d'éventuels problèmes, il est important de bien comprendre le processus de génération du fichier .bsc.  
  
 Lors de la génération d'un fichier d'informations de consultation, BSCMAKE tronque les fichiers .sbr pour qu'ils aient une longueur nulle.  Si le même fichier est généré à nouveau, un fichier .sbr de longueur nulle \(vide\) indique à BSCMAKE qu'il n'a aucune contribution à apporter.  BSCMAKE sait ainsi qu'il n'est pas nécessaire de mettre à jour cette partie du fichier et qu'une génération incrémentielle est suffisante.  Lors de chaque génération \(sauf si l'option \/n est spécifiée\), BSCMAKE essaie d'abord d'effectuer une mise à jour incrémentielle du fichier en utilisant uniquement les fichiers .sbr qui ont évolué.  
  
 BSCMAKE recherche un fichier .bsc portant le nom spécifié avec l'option \/o.  Si cette option n'est pas spécifiée, BSCMAKE recherche un fichier d'extension .bsc dont le nom est identique à celui du premier fichier .sbr.  Si ce fichier existe, BSCMAKE effectue une génération incrémentielle du fichier d'informations de consultation en utilisant uniquement les fichiers .sbr qui apportent de nouvelles informations.  Si ce fichier n'existe pas, BSCMAKE effectue une génération complète utilisant tous les fichiers .sbr.  Les divers types de générations obéissent aux règles suivantes :  
  
-   Pour qu'une génération complète réussisse, tous les fichiers .sbr doivent exister et ne pas être tronqués.  Si un fichier .sbr est tronqué, vous devez le régénérer \(par recompilation ou assemblage\) avant d'exécuter BSCMAKE.  
  
-   Pour qu'une génération incrémentielle réussisse, le fichier .bsc doit exister.  Tous les fichiers .sbr contributeurs \(même vides\) doivent exister et être spécifiés sur la ligne de commande de BSCMAKE.  Si vous omettez un fichier .sbr sur la ligne de commande, BSCMAKE élimine sa contribution au fichier .bsc.  
  
## Voir aussi  
 [Génération d'un fichier .bsc](../../build/reference/building-a-dot-bsc-file.md)