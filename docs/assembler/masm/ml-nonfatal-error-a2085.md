---
title: "ML Nonfatal Error A2085 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2085"
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Nonfatal Error A2085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**instruction ou registre n'est reçu dans le mode actuel de l'UC**  
  
 Une tentative d'utiliser une instruction, un registre, ou un mot clé qui n'était pas valide pour le mode de processeur actuel.  
  
 par exemple, les registres 32 bits requièrent [.386](../../assembler/masm/dot-386.md) ou en haut.  Le contrôle enregistre tels que CR0 requièrent mode privilégié [.386P](../../assembler/masm/dot-386p.md) ou en haut.  cette erreur sera également générée pour les mots clés de **NEAR32**, de **FAR32**, et d' **APPARTEMENT** , qui requièrent.**386** ou en haut.  
  
## Voir aussi  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)