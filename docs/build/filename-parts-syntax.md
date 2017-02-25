---
title: "Syntaxe des &#233;l&#233;ments d&#39;un nom de fichier | Microsoft Docs"
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
  - "syntaxe des éléments d'un nom de fichier dans NMAKE"
  - "programme NMAKE, syntaxe"
  - "syntaxe, éléments d'un nom de fichier"
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Syntaxe des &#233;l&#233;ments d&#39;un nom de fichier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La syntaxe des éléments d'un nom de fichier dans les commandes représente les composants du premier nom de fichier dépendant \(il peut s'agir d'un dépendant implicite\).  Les composants du nom de fichier sont le lecteur, le chemin d'accès, le nom de base et l'extension spécifiée pour le fichier et non telle qu'elle existe sur le disque.  Utilisez **%s** pour représenter le nom de fichier complet.  Utilisez **%&#124;**\[*parties*\]**F** \(un caractère barre verticale suit le signe de pourcentage\) pour représenter des éléments du nom de fichier, où *parties* peut correspondre à zéro ou plusieurs lettres parmi les suivantes, dans un ordre quelconque.  
  
|Lettre|Description|  
|------------|-----------------|  
|Pas de lettre|Nom complet \(identique à **%s**\)|  
|**d**|Lecteur|  
|**p**|Chemin d'accès|  
|**f**|Nom de base du fichier|  
|**e**|Extension du fichier|  
  
 Par exemple, si le nom de fichier est c:\\prog.exe :  
  
-   %s correspond à c:\\prog.exe  
  
-   %&#124;F correspond à c:\\prog.exe  
  
-   %&#124;dF correspond à c  
  
-   %&#124;pF correspond à c:\\  
  
-   %&#124;fF correspond à prog  
  
-   %&#124;eF correspond à exe  
  
## Voir aussi  
 [Commandes dans un makefile](../build/commands-in-a-makefile.md)