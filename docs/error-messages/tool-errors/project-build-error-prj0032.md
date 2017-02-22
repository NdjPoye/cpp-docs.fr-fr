---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0032 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0032"
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur de g&#233;n&#233;ration de projet PRJ0032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La propriété 'Sorties' de l'étape de build personnalisée au niveau du projet contenait 'macro', dont l'évaluation donne 'expansion\_macro'.  
  
 Une étape de build personnalisée effectuée sur un projet s'est traduite par un résultat erroné, sans doute lié à un problème d'évaluation de macros.  Cette erreur peut également vouloir dire que le chemin d'accès est incorrect, ou bien qu'il contient des caractères ou une combinaison de caractères non conformes.  
  
 Pour résoudre ce problème, corrigez la macro ou la spécification du chemin d'accès.  Le chemin d'accès évalué est le chemin d'accès absolu du répertoire du projet.