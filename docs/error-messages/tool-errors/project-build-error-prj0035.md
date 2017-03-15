---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0035 | Microsoft Docs"
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
  - "PRJ0035"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0035"
ms.assetid: 0667116d-338c-40a4-972c-da875f778cb5
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur de g&#233;n&#233;ration de projet PRJ0035
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le fichier XML 'fichier' contient du code Unicode qui n'a pas pu être traduit dans la page de codes ANSI de l'utilisateur.  
  
 ***Contenu UNICODE du fichier***  
  
 ***fichier***  est le fichier XML créé comme ligne de commande pour l'outil de déploiement Web.  
  
 Le système de projet a trouvé dans certaines propriétés de la page de propriétés Déploiement Web des caractères Unicode qu'il n'est pas possible de traduire correctement en code ANSI.  
  
 Pour corriger cette erreur, mettez à jour le contenu de la propriété de façon à utiliser ANSI ou installez la page de codes sur votre ordinateur et définissez\-la en tant que valeur système par défaut.