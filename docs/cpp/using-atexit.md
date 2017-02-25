---
title: "Utilisation d&#39;atexit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "atexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atexit (fonction)"
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Utilisation d&#39;atexit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Avec la fonction [atexit](../c-runtime-library/reference/atexit.md), vous pouvez spécifier une fonction de sortie de traitement qui s'exécute avant l'arrêt du programme.  Aucun objet statique global initialisé avant l'appel à `atexit` n'est détruit avant l'exécution de la fonction de sortie de traitement.  
  
## Voir aussi  
 [Considérations supplémentaires sur la terminaison](../cpp/additional-termination-considerations.md)