---
title: "Erreur irr&#233;cup&#233;rable NMAKE U1056 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1056"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1056"
ms.assetid: da855728-b69e-413c-83ed-df912126215e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur irr&#233;cup&#233;rable NMAKE U1056
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de trouver le processeur de commandes  
  
 L'interpréteur de commandes ne figure pas dans le chemin spécifié dans les variables d'environnement **COMSPEC** et **PATH**.  
  
 NMAKE utilise COMMAND.COM ou CMD.EXE comme interpréteur de commandes lors de l'exécution des commandes.  Il recherche l'interpréteur de commandes d'abord dans le chemin défini dans **COMSPEC**.  Si **COMSPEC** n'existe pas, NMAKE recherche dans les répertoires spécifiés dans **PATH**.