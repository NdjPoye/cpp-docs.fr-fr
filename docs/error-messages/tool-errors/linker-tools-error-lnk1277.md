---
title: "Erreur des outils &#201;diteur de liens LNK1277 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1277"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1277"
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur des outils &#201;diteur de liens LNK1277
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

enregistrement objet introuvable dans pgd \(NomFichier\)  
  
 Lors de l'utilisation de [\/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), le chemin d'accès d'un des fichiers d'entrée .lib, def ou .obj était différent du chemin d'accès sur lequel ils ont été détectés lors de l'exécution de \/LTCG:PGINSTRUMENT.  Cela peut s'expliquer par une modification de la variable d'environnement LIB après \/LTCG:PGINSTRUMENT.  Le chemin d'accès complet des fichiers d'entrée est stocké dans le fichier .pgd.  
  
 \/LTCG: PGOPTIMIZE exige que les entrées soient identiques à la phase \/LTCG:PGINSTRUMENT.  
  
 Pour remédier à cet avertissement, effectuez l'une des opérations suivantes :  
  
-   Exécutez \/LTCG:PGINSTRUMENT, réalisez à nouveau toutes les séries de tests et exécutez \/LTCG:PGOPTIMIZE.  
  
-   Rétablissez la variable d'environnement LIB dans l'état où elle se trouvait lors de l'exécution de \/LTCG:PGINSTRUMENT.  
  
 Il n'est pas recommandé de contourner l'erreur LNK1277 en utilisant \/LTCG:PGUPDATE.