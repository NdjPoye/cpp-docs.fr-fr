---
title: "Avertissement du compilateur (niveau 1) C4420 | Microsoft Docs"
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
  - "C4420"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4420"
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4420
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : opérateur non disponible, remplacé par 'opérateur' ; le contrôle à l'exécution peut être compromis  
  
 Cet avertissement est généré quand vous utilisez [\/RTCv](../../build/reference/rtc-run-time-error-checks.md) \(contrôle de new\/delete sur vecteur\) et qu'aucune forme vecteur n'est trouvée.  Dans ce cas, c'est la forme non vecteur qui est utilisée.  
  
 Pour que \/RTCv fonctionne correctement, le compilateur doit toujours appeler la forme vecteur de [new](../../cpp/new-operator-cpp.md)\/[delete](../../cpp/delete-operator-cpp.md) si la syntaxe vecteur a été utilisée.