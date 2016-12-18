---
title: "O&#249; d&#233;finir des macros | Microsoft Docs"
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
  - "définir des macros"
  - "macros, NMAKE"
  - "programme NMAKE, définir des macros"
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# O&#249; d&#233;finir des macros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définissez les macros dans une ligne de commande, un fichier de commandes, un makefile ou le fichier Tools.ini.  
  
 Dans un makefile ou le fichier Tools.ini, chaque définition de macro doit apparaître sur une ligne séparée et ne peut commencer ni par un espace ni par une tabulation.  Les espaces ou les tabulations entourant le signe égal à sont ignorés.  Tous les [caractères de chaîne](../build/defining-an-nmake-macro.md) sont littéraux, guillemets de délimitation et espaces incorporés compris.  
  
 Dans une ligne de commande ou un fichier de commandes, les espaces et les tabulations délimitent les arguments et ne peuvent pas entourer le signe égal à.  Si la `string` incorpore des espaces ou des tabulations, mettez la chaîne ou la macro entière entre guillemets \(" "\).  
  
## Voir aussi  
 [Définition d'une macro NMAKE](../build/defining-an-nmake-macro.md)