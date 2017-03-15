---
title: "Erreur irr&#233;cup&#233;rable NMAKE U1064 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1064"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1064"
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur irr&#233;cup&#233;rable NMAKE U1064
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MAKEFILE non trouvé et aucune cible spécifiée  
  
 La ligne de commande NMAKE ne spécifie ni makefile ni cible, et le répertoire en cours ne contient pas de fichier appelé MAKEFILE.  
  
 NMAKE exige un makefile ou une cible de ligne de commande \(ou les deux\).  Pour mettre un makefile à la disposition de NMAKE, spécifiez l'option \/F ou placez un fichier nommé MAKEFILE dans le répertoire en cours.  NMAKE peut créer une cible de ligne de commande en appliquant une règle d'inférence si aucun makefile n'est fourni.