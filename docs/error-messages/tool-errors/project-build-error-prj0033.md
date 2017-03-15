---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0033 | Microsoft Docs"
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
  - "PRJ0033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0033"
ms.assetid: 84d4a052-0586-4b78-9315-81c1e8386c1e
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur de g&#233;n&#233;ration de projet PRJ0033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La propriété 'Dépendances supplémentaires' de l'étape de build personnalisée du fichier 'fichier' contenait 'macro', dont l'évaluation donne 'expansion\_macro'.  
  
 Une étape de build personnalisée effectuée sur un fichier contenait une erreur dans ses dépendances supplémentaires, sans doute liée à un problème d'évaluation de macros.  Cette erreur peut également vouloir dire que le chemin d'accès est incorrect, ou bien qu'il contient des caractères ou une combinaison de caractères non conformes.  
  
 Pour résoudre ce problème, corrigez la macro ou la spécification du chemin d'accès.  Le chemin d'accès évalué est le chemin d'accès absolu du répertoire du projet.