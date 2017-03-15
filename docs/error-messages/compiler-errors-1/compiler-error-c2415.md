---
title: "Erreur du compilateur C2415 | Microsoft Docs"
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
  - "C2415"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2415"
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2415
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

type d'opérande incorrect  
  
 L'opcode n'utilise pas d'opérandes de ce type.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  L'opcode ne prend pas en charge le nombre d'opérandes utilisé.  Vérifiez le nombre d'opérandes correct dans un manuel de référence de langage assembleur.  
  
2.  Les derniers processeurs prennent en charge l'instruction avec des types supplémentaires.  Modifiez l'option [\/arch \(Architecture d'UC minimale\)](../../build/reference/arch-minimum-cpu-architecture.md) pour utiliser le processeur le plus récent.