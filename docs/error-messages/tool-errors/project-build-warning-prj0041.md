---
title: "Avertissement de g&#233;n&#233;ration de projet PRJ0041 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0041"
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement de g&#233;n&#233;ration de projet PRJ0041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Impossible de trouver la dépendance manquante 'dépendance' pour le fichier 'fichier'.Votre projet peut être compilé, mais peut sembler obsolète tant que ce fichier est introuvable.  
  
 Un fichier \(fichier de ressources ou fichier .idl\/.odl, par exemple\) contenait une instruction include que le système de projet n'a pas pu résoudre.  
  
 Le système de projet ne traitant pas les instructions de préprocesseur \(\#if, par exemple\), l'instruction concernée pourrait ne pas faire partie de la génération.  
  
 Pour corriger cet avertissement, supprimez tout le code non nécessaire dans les fichiers .rc ou ajoutez des fichiers d'espace réservé du nom approprié.