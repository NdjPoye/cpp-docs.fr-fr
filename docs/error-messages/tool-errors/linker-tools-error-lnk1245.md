---
title: "Erreur des outils &#201;diteur de liens LNK1245 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1245"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1245"
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur des outils &#201;diteur de liens LNK1245
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

sous\-système 'SousSystème' spécifié non valide ; \/SUBSYSTEM doit être WINDOWS, WINDOWSCE, ou CONSOLE  
  
 L'option [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) a été utilisée pour compiler l'objet et une des conditions suivantes a été rencontrée :  
  
-   Un point d'entrée personnalisé a été défini \([\/ENTRY](../../build/reference/entry-entry-point-symbol.md)\), de sorte que l'éditeur de liens n'a pas pu déduire de sous\-système.  
  
-   Une valeur qui n'est pas valide les objets \/clr a été est passée à l'option de l'éditeur de liens [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md).  
  
 Dans les deux cas, la solution consiste à spécifier une valeur valide pour l'option de l'éditeur de liens \/SUBSYSTEM.