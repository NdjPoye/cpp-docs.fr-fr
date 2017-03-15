---
title: "Caract&#232;res sp&#233;ciaux dans les macros | Microsoft Docs"
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
  - "caractères spéciaux, dans les macros NMAKE"
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Caract&#232;res sp&#233;ciaux dans les macros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le signe dièse \(\#\) placé après une définition indique un commentaire.  Pour spécifier un signe dièse littéral dans une macro, utilisez un signe insertion \(^\), comme dans ^\#.  
  
 Le signe dollar \($\) spécifie un appel de macro.  Pour spécifier un $ littéral, utilisez $$.  
  
 Pour étendre une définition sur une nouvelle ligne, terminez la ligne par une barre oblique inverse \(\\\).  Lorsque la macro est appelée, la barre oblique inverse plus le caractère de saut de ligne sont remplacés par un espace.  Pour spécifier une barre oblique inverse littérale à la fin de la ligne, faites\-la précéder par un signe insertion \(^\) ou faites\-la suivre par un spécificateur de commentaire \(\#\).  
  
 Pour définir un caractère de saut de ligne littéral, terminez la ligne par un signe insertion \(^\), comme suit :  
  
```  
CMDS = cls^  
dir  
```  
  
## Voir aussi  
 [Définition d'une macro NMAKE](../build/defining-an-nmake-macro.md)