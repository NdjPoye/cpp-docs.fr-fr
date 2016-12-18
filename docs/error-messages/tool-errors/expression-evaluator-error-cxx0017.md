---
title: "&#201;valuateur d&#39;expression, erreur CXX0017 | Microsoft Docs"
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
  - "CXX0017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0017"
  - "CXX0017"
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &#201;valuateur d&#39;expression, erreur CXX0017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

symbole non trouvé  
  
 Un symbole spécifié dans une expression est introuvable.  
  
 L'une des causes possibles de cette erreur est le non\-respect de la casse dans le nom du symbole.  Dans la mesure où les langages C et C\+\+ respectent la casse, un nom de symbole doit être fourni avec exactement la même casse que sa définition dans le source.  
  
 Cette erreur peut se produire lorsque vous essayez de convertir le type d'une variable pour surveiller celle\-ci pendant le débogage.  `typedef` déclare un nouveau nom de type mais ne définit pas un nouveau type.  La conversion de type tentée dans le débogueur exige le nom d'un type défini.  
  
 Erreur identique à CAN0017.  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Assurez\-vous que le symbole est déjà déclaré au moment où il est utilisé dans le programme.  
  
2.  Pour effectuer un cast des variables dans le débogueur, utilisez un nom de type réel plutôt qu'un nom défini par `typedef`.