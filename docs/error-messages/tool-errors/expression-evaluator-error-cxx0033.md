---
title: "&#201;valuateur d&#39;expression, erreur CXX0033 | Microsoft Docs"
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
  - "CXX0033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0033"
  - "CXX0033"
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &#201;valuateur d&#39;expression, erreur CXX0033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur dans les informations de type OMF  
  
 Le fichier exécutable ne présente pas un format OMF \(Object Module Format\) valide pour le débogage.  
  
 Erreur identique à CAN0033.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Le fichier exécutable n'a pas été créé avec l'éditeur de liens fourni avec cette version de Visual C\+\+.  Rééditez le code objet à l'aide de la version actuelle de LINK.exe.  
  
2.  Le fichier .exe est peut\-être endommagé.  Recompilez et rééditez le programme.