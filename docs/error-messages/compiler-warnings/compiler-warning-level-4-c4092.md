---
title: "Avertissement du compilateur (niveau 4) C4092 | Microsoft Docs"
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
  - "C4092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4092"
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

sizeof retourne 'unsigned long'  
  
 L'opérande de l'opérateur `sizeof` était très grand ; par conséquent, `sizeof` a retourné unsigned **long**.  Cet avertissement apparaît sous les extensions Microsoft \([\/Ze\)](../../build/reference/za-ze-disable-language-extensions.md).  Sous compatibilité ANSI \(\/Za\), le résultat est tronqué.