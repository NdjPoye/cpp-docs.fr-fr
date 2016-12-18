---
title: "Erreur des outils &#201;diteur de liens LNK1223 | Microsoft Docs"
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
  - "LNK1223"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1223"
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1223
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fichier non valide ou endommagé : le fichier contient des contributions .pdata non valides  
  
 Pour les plateformes RISC qui utilisent des pdata, cette erreur survient si le compilateur a émis une section .pdata avec des entrées non triées.  
  
 Pour résoudre ce problème, essayez de compiler sans activer [\/GL \(Whole Program Optimization\)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md).  Les corps de fonction vides peuvent aussi provoquer cette erreur dans certains cas.