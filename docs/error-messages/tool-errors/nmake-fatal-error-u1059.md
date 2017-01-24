---
title: "Erreur irr&#233;cup&#233;rable NMAKE U1059 | Microsoft Docs"
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
  - "U1059"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1059"
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable NMAKE U1059
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de syntaxe : '}' absent dans le fichier dépendant  
  
 Un chemin de recherche d'un dépendant est incorrectement spécifié.  Soit le chemin contient un espace soit l'accolade fermante \(**}**\) a été omise.  
  
 La syntaxe d'une spécification de répertoire d'un dépendant est la suivante  
  
 **{**   
 ***répertoires* }dépendant**  
  
 où `directories` indique un ou plusieurs chemins, chacun séparé par un point\-virgule \(**;**\).  Les espaces ne sont pas admis.  
  
 Si un chemin de recherche est remplacé entièrement ou partiellement par une macro, vérifiez que l'expansion macro ne contient pas d'espaces.