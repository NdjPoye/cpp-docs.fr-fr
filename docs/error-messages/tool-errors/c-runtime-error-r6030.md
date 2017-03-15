---
title: "Erreur d’ex&#233;cution C R6030 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6030"
ms.assetid: 0238a6c3-a033-4046-8adc-f8f99d961153
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur d&#39;ex&#233;cution C R6030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CRT non initialisé  
  
 Cette erreur se produit si vous utilisez le CRT, mais que le code de démarrage CRT n'a pas été exécuté.  Vous pouvez obtenir cette erreur si le commutateur de l'éditeur de liens [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) est utilisé pour substituer l'adresse de démarrage par défaut, habituellement **mainCRTStartup** ou **wmainCRTStartup** pour un EXE console, **WinMainCRTStartup** ou **wWinMainCRTStartup** pour un EXE Windows, ou **\_DllMainCRTStartup** pour une DLL.  À moins que l'une des fonctions précitées ne soit appelée au démarrage, la Runtime C ne sera pas initialisé.