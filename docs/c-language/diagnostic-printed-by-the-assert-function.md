---
title: "Diagnostic affich&#233; par la fonction assert | Microsoft Docs"
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
  - "C"
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Diagnostic affich&#233; par la fonction assert
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.2** Diagnostic imprimé et comportement d'arrêt de la fonction **assert**  
  
 La fonction **assert** imprime un message de diagnostic et appelle la routine **abort** si l'expression est false \(0\).  Le message de diagnostic se présente sous la forme  
  
 **Assertion failed**: *expression***, file** *filename***, line** *linenumber*  
  
 où filename est le nom du fichier source et linenumber est le numéro de ligne de l'assertion qui a échoué dans le fichier source.  Aucune action n'est effectuée si l'expression est vraie \(différente de zéro\).  
  
## Voir aussi  
 [Fonctions des bibliothèques](../c-language/library-functions.md)