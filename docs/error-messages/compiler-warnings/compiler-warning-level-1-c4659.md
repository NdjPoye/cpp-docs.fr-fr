---
title: "Avertissement du compilateur (niveau 1) C4659 | Microsoft Docs"
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
  - "C4659"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4659"
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4659
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma 'pragma' : l'utilisation du segment réservé 'segment' a un comportement indéfini, utilisez \#pragma comment\(linker, ...\)  
  
 L'option .drectve a été utilisée pour passer une option à l'Éditeur de liens.  Utilisez plutôt pragma [comment](../../preprocessor/comment-c-cpp.md) pour passer une option à l'Éditeur de liens.  
  
```  
// C4659.cpp  
// compile with: /W1 /LD  
#pragma code_seg(".drectve")   // C4659  
```