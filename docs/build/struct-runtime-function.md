---
title: "RUNTIME_FUNCTION, structure | Microsoft Docs"
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
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# RUNTIME_FUNCTION, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La gestion des exceptions basée sur une table exige une entrée de table pour toutes les fonctions qui allouent de l'espace de pile ou appellent une autre fonction \(par exemple, les fonctions non\-feuille\).  Les entrées d'une table de fonctions ont le format suivant :  
  
|||  
|-|-|  
|ULONG|Adresse de début de fonction|  
|ULONG|Adresse de fin de fonction|  
|ULONG|Adresse des informations de déroulement|  
  
 La structure RUNTIME\_FUNCTION doit être alignée sur un DWORD en mémoire.  Toutes les adresses sont relatives à l'image, c'est\-à\-dire qu'elles sont des offsets de 32 bits de l'adresse de départ de l'image qui contient l'entrée de la table de fonctions.  Ces entrées sont triées et placées dans la section .pdata d'une image PE32\+.  Pour les fonctions générées dynamiquement \[Compilateurs JIT\], le runtime prenant en charge ces fonctions doit utiliser RtlInstallFunctionTableCallback ou RtlAddFunctionTable pour fournir cette information au système d'exploitation.  Sinon, cela entraînera une gestion des exceptions et un débogage de processus peu fiables.  
  
## Voir aussi  
 [Données de déroulement pour la gestion des exceptions et la prise en charge du débogueur](../build/unwind-data-for-exception-handling-debugger-support.md)