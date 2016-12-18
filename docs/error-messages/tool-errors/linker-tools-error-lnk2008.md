---
title: "Erreur des outils &#201;diteur de liens LNK2008 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2008"
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK2008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cible de correction non alignée 'nom\_symbole'  
  
 LINK a trouvé une cible de correction dans votre fichier objet qui n'était pas alignée correctement.  
  
 Cette erreur peut être provoquée par un alignement de section personnalisé \(par exemple, \#pragma [pack](../../preprocessor/pack.md)\), un modificateur [align](../../cpp/align-cpp.md) ou l'utilisation de code en langage assembleur qui modifie l'alignement de d'une section.  
  
 Si votre code n'utilise aucun des éléments mentionnés ci\-dessus, l'erreur peut être provoquée par le compilateur.