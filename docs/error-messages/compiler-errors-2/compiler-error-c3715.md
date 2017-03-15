---
title: "Erreur du compilateur C3715 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3715"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3715"
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3715
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'pointeur' : doit être un pointeur vers 'classe'  
  
 Vous avez spécifié un pointeur dans [\_\_hook](../../cpp/hook.md) ou [\_\_unhook](../../cpp/unhook.md) qui ne pointe pas vers une classe valide.  Pour remédier à cette erreur, vérifiez que vos appels `__hook` et `__unhook` spécifient des pointeurs vers des classes valides.