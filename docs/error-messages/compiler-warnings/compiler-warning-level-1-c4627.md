---
title: "Avertissement du compilateur (niveau&#160;1) C4627 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4627"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4627"
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4627
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\<identificateur\>' : ignoré lors de la recherche d’une utilisation d’un en\-tête précompilé  
  
 Lors de la recherche de l’emplacement d’utilisation d’un en\-tête précompilé, le compilateur a rencontré une directive `#include` pour le fichier Include *\<identificateur\>* . Le compilateur ignore la directive `#include`, mais il émet l’avertissement **C4627** si l’en\-tête précompilé ne contient pas le fichier Include *\<identificateur\>*.  
  
## Voir aussi  
 [Création de fichiers d'en\-tête précompilés](../../build/reference/creating-precompiled-header-files.md)