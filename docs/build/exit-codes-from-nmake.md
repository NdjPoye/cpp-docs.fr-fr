---
title: "Codes de sortie de NMAKE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codes de sortie"
  - "programme NMAKE, codes de sortie"
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Codes de sortie de NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE retourne les codes de sortie suivants :  
  
|Code|Signification|  
|----------|-------------------|  
|0|Aucune erreur \(probablement un avertissement\)|  
|1|Génération incomplète \(émis seulement quand l'option \/K est utilisée\)|  
|2|Erreur de programme, probablement due à l'une des causes suivantes :|  
||-   Erreur de syntaxe dans le makefile|  
||-   Erreur ou code de sortie provenant d'une commande|  
||-   Interruption déclenchée par l'utilisateur|  
|4|Erreur système — Mémoire insuffisante|  
|255|Cible obsolète \(émis seulement quand l'option \/Q est utilisée\)|  
  
## Voir aussi  
 [Exécution de NMAKE](../build/running-nmake.md)