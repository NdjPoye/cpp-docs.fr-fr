---
title: "Jeux de caract&#232;res cod&#233;s sur un octet et multioctets | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.character.multibyte"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "jeux de caractères (C++), multioctets"
  - "jeux de caractères (C++), octet unique"
  - "MBCS (C++), à propos de MBCS"
  - "SBCS (jeu de caractères codé sur un octet)"
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Jeux de caract&#232;res cod&#233;s sur un octet et multioctets
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le jeu de caractères ASCII définit les caractères de la plage 0x00 \- 0x7F.  Il existe d'autres jeux de caractères, par exemple le jeu de caractères européen, qui définissent les caractères de la plage 0x00 à 0x7F de la même façon que le jeu de caractères ASCII et qui définissent également un jeu de caractères étendus de 0x80 à 0xFF.  C'est pourquoi, un jeu de caractères codé sur un octet \(`SBCS`\), 8 bits, est suffisant pour représenter le jeu de caractères ASCII, ainsi que les jeux de caractères pour de nombreuses langues européennes.  Cependant, certains jeux de caractères pour des langues non européennes, par exemple le kanji japonais, comprennent beaucoup plus de caractères que ceux que peut représenter un schéma d'encodage sur un octet et nécessitent un encodage de jeu de caractères multioctets \(`MBCS`\).  
  
> [!NOTE]
>  De nombreuses routines `SBCS` dans la bibliothèque Runtime de Microsoft gère des octets multioctets, et des chaînes de caractères associées.  De nombreux jeux de caractères multioctets définnissent le jeu de caractères ASCII comme un sous\-ensemble.  Dans de nombreux jeux de caractères multioctets, chaque caractère de la plage 0x00 – 0x7F est identique au caractère qui a la même valeur dans le jeu de caractères ASCII.  Par exemple, dans les chaînes de caractères ASCII et MBCS, les chaînes de caractères `ASCII` et `MBCS`, le caractère sur un octet `NULL` \('\\0'\) a la valeur 0x00 et indique le caractère de fin null.  
  
 Un jeu de caractères multioctets peut se composer d'un octet et de caractères sur deux octets.  Donc une chaîne de caractères multi\-octets peut contenir une combinaison de caractères sur un ou deux octets.  Un caractères multioctets sur deux octets a un lead octet \(KPI\) et un octet de fin.  Dans un jeu de caractères multioctets, les octets de tête font partie d'une plage spécifique, ainsi que les octets de queue.  Lorsque ces plages se superposent, il peut être nécessaire d'évaluer le contexte pour déterminer si un octet donné fonctionne en tant qu'octet de tête ou octet de queue.  
  
## Voir aussi  
 [Internationalisation](../c-runtime-library/internationalization.md)   
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)