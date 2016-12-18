---
title: "Erreur du compilateur C2414 | Microsoft Docs"
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
  - "C2414"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2414"
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2414
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

nombre d'opérandes non conforme  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  L'opcode ne prend pas en charge le nombre d'opérandes utilisé.  Vérifiez le nombre d'opérandes correct dans un manuel de référence de langage assembleur.  
  
2.  Un processeur plus récent prend en charge l'instruction avec un nombre d'opérandes différent.  Modifiez l'option [\/arch \(Architecture d'UC minimale\)](../../build/reference/arch-minimum-cpu-architecture.md) pour utiliser le processeur le plus récent.