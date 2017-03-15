---
title: "Appel de fonctions C++ dans un assembly inline | Microsoft Docs"
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
  - "__asm (mot clé) (C++), appeler des fonctions"
  - "appels de fonction, fonctions C++"
  - "appels de fonction, dans l'assembleur inline"
  - "fonctions (C++), appeler dans l'assembleur inline"
  - "assembleur inline, appeler des fonctions"
  - "Visual C++, fonctions"
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Appel de fonctions C++ dans un assembly inline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Un bloc `__asm` peut appeler uniquement des fonctions C\+\+ globales qui ne sont pas surchargées.  Si vous appelez une fonction C\+\+ globale surchargée ou une fonction membre C\+\+, le compilateur génère une erreur.  
  
 Vous pouvez également appeler toutes les fonctions déclarées avec la liaison **extern "C"**.  Cela permet à un bloc `__asm` au sein d'un programme C\+\+ d'appeler les fonctions de la bibliothèque C, car tous les fichiers d'en\-tête standard déclarent les fonctions de bibliothèque comme ayant une liaison **extern "C"**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Assembleur inline](../../assembler/inline/inline-assembler.md)