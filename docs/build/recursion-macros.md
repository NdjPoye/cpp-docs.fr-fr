---
title: "Macros r&#233;cursives | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "macros, récurrence"
  - "programme NMAKE, macros récursives"
  - "macros récursives"
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Macros r&#233;cursives
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez les macros de récursivité pour appeler NMAKE de manière récursive.  Les sessions récursives héritent des macros de ligne de commande et des variables d'environnement ainsi que des informations concernant Tools.ini.  Elles n'héritent pas des règles d'inférence définies dans un makefile ni des spécifications **.SUFFIXES** et **.PRECIOUS**.  Pour passer des macros à une session NMAKE récursive, définissez une variable d'environnement en plaçant SET devant l'appel récursif, définissez une macro dans la commande pour l'appel récursif ou définissez une macro dans Tools.ini.  
  
|Macro|Définition|  
|-----------|----------------|  
|**MAKE**|Commande utilisée initialement pour appeler NMAKE.<br /><br /> La macro $\(MAKE\) fournit le chemin d'accès complet à nmake.exe.|  
|**MAKEDIR**|Répertoire actif où NMAKE a été appelé.|  
|**MAKEFLAGS**|Options appliquées.  Utilisez cette macro comme suit : `/$(MAKEFLAGS)`.  Notez, le \/F n'est pas inclus.|  
  
## Voir aussi  
 [Macros spéciales de NMAKE](../build/special-nmake-macros.md)