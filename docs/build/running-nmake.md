---
title: "Ex&#233;cution de NMAKE | Microsoft Docs"
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
  - "fichiers de commandes"
  - "fichiers de commandes, NMAKE"
  - "programme NMAKE, exécuter"
  - "programme NMAKE, cibles"
  - "fichiers réponse, NMAKE"
  - "cibles"
  - "cibles, générer"
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ex&#233;cution de NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
NMAKE [option...] [macros...] [targets...] [@commandfile...]  
```  
  
## Notes  
 NMAKE génère uniquement les *cibles* spécifiées ou, si aucune cible n'est définie, la première cible rencontrée dans le makefile.  La première cible du makefile peut être une [pseudocible](../build/pseudotargets.md) qui génère d'autres cibles.  NMAKE utilise les makefiles définis à l'aide de l'option \/F ; si l'option \/F n'est pas spécifiée, il utilise le makefile du répertoire en cours.  Si aucun makefile n'est défini, il applique les règles d'inférence pour générer des *cibles* à partir de la ligne de commande.  
  
 Le fichier texte `commandfile` \(ou fichier réponse\) contient l'entrée de la ligne de commande.  D'autres entrées peuvent précéder ou suivre @`commandfile`.  L'utilisation d'un chemin d'accès est autorisée.  Dans `commandfile`, les sauts de ligne sont considérés comme des espaces.  Mettez les définitions de macros entre guillemets si elles contiennent des espaces.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
 [Options de NMAKE](../build/nmake-options.md)  
  
 [Tools.ini et NMAKE](../build/tools-ini-and-nmake.md)  
  
 [Codes de sortie de NMAKE](../build/exit-codes-from-nmake.md)  
  
## Voir aussi  
 [Référence NMAKE](../build/nmake-reference.md)