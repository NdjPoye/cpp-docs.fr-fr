---
title: "Mots r&#233;serv&#233;s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "code"
  - "CONFORMING"
  - "DISCARDABLE"
  - "Description"
  - "base"
  - "APPLOADER"
  - "Data"
  - "DYNAMIC"
  - "DEV386"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .def (C++), mots réservés"
  - "fichiers def (C++), mots réservés"
  - "éditeur de liens (C++), mots réservés"
  - "mots réservés (C++)"
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Mots r&#233;serv&#233;s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les mots suivants sont réservés par l'éditeur de liens.  Ces noms ne peuvent être utilisés comme arguments dans les [instructions de définition de module](../../build/reference/module-definition-dot-def-files.md) que s'ils sont placés entre guillemets doubles \(""\).  
  
||||  
|-|-|-|  
|**APPLOADER**1|**INITINSTANCE**2|**PRELOAD**|  
|**BASE**|**IOPL**|**PRIVATE**|  
|**CODE**|**LIBRARY**1|**PROTMODE**2|  
|**CONFORMING**|**LOADONCALL**1|**PURE**1|  
|**DATA**|**LONGNAMES**2|**READONLY**|  
|**DESCRIPTION**|`MOVABLE`1|**READWRITE**|  
|**DEV386**|**MOVEABLE**1|**REALMODE**1|  
|**DISCARDABLE**|**MULTIPLE**|**RESIDENT**|  
|**DYNAMIC**|**NOM**|**RESIDENTNAME**1|  
|**EXECUTE\-ONLY**|**NEWFILES**2|**SECTIONS**|  
|**EXECUTEONLY**|`NODATA`1|**SEGMENTS**|  
|**EXECUTEREAD**|**NOIOPL**1|**SHARED**|  
|**EXETYPE**|**NONAME**|**SINGLE**|  
|**EXPORTS**|**NONCONFORMING**1|**STACKSIZE**|  
|**FIXED**1|**NONDISCARDABLE**|**STUB**|  
|**FUNCTIONS**2|**NONE**|**VERSION**|  
|**HEAPSIZE**|**NONSHARED**|**WINDOWAPI**|  
|**IMPORTS**|**NOTWINDOWCOMPAT**1|**WINDOWCOMPAT**|  
|**IMPURE**1|**OBJECTS**|**WINDOWS**|  
|**INCLUDE**2|**OLD**1||  
  
 1 L'éditeur de liens émet un avertissement \(« ignoré »\) lorsqu'il trouve ce terme.  Toutefois, le mot est toujours réservé.  
  
 2 L'éditeur de liens ignore ce mot, mais n'émet aucun avertissement.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)