---
title: "Op&#233;rateurs de pr&#233;processeur | Microsoft Docs"
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
  - "opérateurs (C++), préprocesseur"
  - "opérateurs de préprocesseur"
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Op&#233;rateurs de pr&#233;processeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quatre opérateurs spécifiques aux préprocesseurs sont utilisés dans le contexte de la directive `#define` \(consultez la liste suivante pour un résumé de chaque\).  Les opérateurs d'enchaînement, de charizing, et de collage de jetons sont traités dans les trois sections suivantes.  Pour plus d'informations sur l'opérateur **Défini**, consultez [Le \#if, le \#elif, le \#else, et les directives de \#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).  
  
|Opérateur|Action|  
|---------------|------------|  
|[Opérateur d'enchaînement \(\#\)](../preprocessor/stringizing-operator-hash.md)|Cause la mise entre guillemets doubles de l'argument correspondant|  
|[Opérateur charizing \(\#@\)](../preprocessor/charizing-operator-hash-at.md)|Cause la mise entre guillemets simples de l'argument et son traitement en tant que un caractère \(lMicrosoft Specific\)|  
|[Opérateur de collage de jetons \(\#\#\)](../preprocessor/token-pasting-operator-hash-hash.md)|Autorise les jetons utilisés comme arguments à être concaténés pour former d'autres jetons|  
|[opérateur défini](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Simplifie l'écriture d'expressions composées dans certaines macro directives|  
  
## Voir aussi  
 [Directives de préprocesseur](../preprocessor/preprocessor-directives.md)   
 [Macros prédéfinies](../preprocessor/predefined-macros.md)   
 [Référence du préprocesseur C\/C\+\+](../preprocessor/c-cpp-preprocessor-reference.md)