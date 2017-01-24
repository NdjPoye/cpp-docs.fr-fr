---
title: "Conventions d&#39;appel obsol&#232;tes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__fortran"
  - "__pascal"
  - "__syscall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__fortran (mot clé) (C++)"
  - "__pascal (mot clé) (C++)"
  - "__syscall (mot clé) (C++)"
  - "conventions d'appel, obsolète"
  - "WINAPI"
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conventions d&#39;appel obsol&#232;tes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Les conventions d'appel **\_\_pascal**, **\_\_fortran** et **\_\_syscall** ne sont plus prises en charge.  Vous pouvez émuler leurs fonctionnalités en utilisant l'une des conventions d'appel prises en charge et les options appropriées de l'Éditeur de liens.  
  
 WINDOWS.H prend désormais en charge la macro **WINAPI**, qui effectue la traduction dans la convention d'appel appropriée pour la cible.  Utilisez **WINAPI** où vous avez utilisé précédemment **PASCAL** ou **\_\_far \_\_pascal**.  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Passage des arguments et conventions de dénomination](../cpp/argument-passing-and-naming-conventions.md)