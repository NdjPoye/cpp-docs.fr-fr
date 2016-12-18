---
title: "Avertissement du compilateur (niveau 1) C4124 | Microsoft Docs"
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
  - "C4124"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4124"
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4124
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_fastcall avec contrôle de pile est inefficace  
  
 Le mot clé `__fastcall` a été utilisé avec le contrôle de pile activé.  
  
 La convention `__fastcall` génère du code plus rapide, mais le contrôle de pile ralentit le code.  Lors de l'utilisation de `__fastcall`, désactivez le contrôle de pile avec le pragma **check\_stack** ou \/Gs.  
  
 Cet avertissement n'est généré que pour la première fonction déclarée dans ces conditions.