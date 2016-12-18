---
title: "Flux d&#39;octets et flux larges | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Byte and Wide Streams"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "flux d'octets"
  - "flux larges"
ms.assetid: 61ef0587-4cbc-4eb8-aae5-4c298dbbc6f9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Flux d&#39;octets et flux larges
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un flux d'octets traite un fichier comme séquence d'octets.  Dans le cadre du programme, le flux de données est la même séquence d'octets.  
  
 En revanche, un flux de données traite un fichier comme séquence de caractères multioctets généralisés, qui peuvent avoir une large gamme de règles d'encodage. \(Le texte et les fichiers binaires sont toujours lus et écrits comme décrit précédemment.\) Dans le cadre de programme, le flux ressemble à la série de caractères larges correspondants.  Les conversions entre les deux représentations se produisent dans la bibliothèque Standard C.  Les règles de conversion peuvent être modifiées, en principe, par un appel à [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) qui modifie la catégorie `LC_CTYPE`.  Chaque flux large détermine les règles de conversion lorsqu'il devient orienté large, et conserve ces règles même si la catégorie `LC_CTYPE` change ultérieurement.  
  
 Le positionnement dans un flux large souffre les mêmes limitations que pour les flux de texte.  De plus, l'indicateur d'emplacement de fichier peut potentiellement avoir à traiter un encodage dépendant de l'état.  En général, il comprend un décalage d'octets dans le flux de données et un objet de type `mbstate_t`.  Par conséquent, la seule méthode fiable pour obtenir une position de fichier dans un flux large est d'appeler [fgetpos](../c-runtime-library/reference/fgetpos.md), la seule méthode fiable pour restaurer une position ainsi obtenue est d'appeler [fsetpos](../c-runtime-library/reference/fsetpos.md).  
  
## Voir aussi  
 [Fichiers et flux](../c-runtime-library/files-and-streams.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)