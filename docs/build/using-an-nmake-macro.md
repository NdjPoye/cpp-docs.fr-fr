---
title: "Utilisation d&#39;une macro NMAKE | Microsoft Docs"
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
  - "macros, NMAKE"
  - "NMAKE (macros), utilisation"
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Utilisation d&#39;une macro NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour utiliser une macro, mettez son nom entre parenthèses précédé d'un signe dollar \($\), comme ci\-\-dessous.  
  
## Syntaxe  
  
```  
$(macroname)  
```  
  
## Remarques  
 Les espaces ne sont pas admis.  Les parenthèses sont facultatives si *macroname* est un caractère unique.  La chaîne de définition remplace $\(*macroname*\) ; une macro non définie est remplacée par une chaîne nulle.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
 [Substitution macro](../build/macro-substitution.md)  
  
## Voir aussi  
 [NMAKE et les macros](../build/macros-and-nmake.md)