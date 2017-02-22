---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0036 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0036"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0036"
ms.assetid: ee215cd1-2d66-474d-9a63-b9096f1c4923
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur de g&#233;n&#233;ration de projet PRJ0036
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La propriété 'Fichiers supplémentaires' de l'outil de déploiement Web contenait une entrée non valide.  
  
 La propriété Fichiers supplémentaires sur la page de propriétés Déploiement Web contenait une erreur, sans doute liée à un problème d'évaluation de macros.  Cette erreur peut également vouloir dire que le chemin d'accès est incorrect, ou bien qu'il contient des caractères ou une combinaison de caractères non conformes.  
  
 Pour résoudre ce problème, corrigez la macro ou la spécification du chemin d'accès.  Le chemin d'accès évalué est le chemin d'accès absolu du répertoire du projet.  
  
 Cette erreur peut également signifier que l'un des fichiers référencés n'existe pas.