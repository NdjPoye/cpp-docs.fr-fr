---
title: "Avertissement du compilateur (niveau&#160;4) C4718 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4718"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4718"
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4718
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function call' : un appel récurrent n’a pas d’effets secondaires, suppression  
  
 Une fonction contient un appel récurrent, mais n’a pas d’effets secondaires. Un appel à cette fonction est en cours de suppression. L’exactitude du programme n’est pas affectée ; par contre, son comportement l’est. Si le fait de laisser l’appel peut provoquer une exception de dépassement de capacité de la pile d’exécution, la suppression de l’appel élimine ce risque.