---
title: "Erreur du compilateur C2019 | Microsoft Docs"
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
  - "C2019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2019"
ms.assetid: 4f37b1e1-9eca-418f-a4c3-141e8512d7b6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

directive du préprocesseur attendue, 'caractère' rencontré  
  
 Le caractère suivait un signe `#` mais ce n'est pas la première lettre d'une directive de préprocesseur.  
  
 L'exemple suivant génère l'erreur C2019 :  
  
```  
// C2019.cpp  
#!define TRUE 1   // C2019  
```  
  
 Résolution possible :  
  
```  
// C2019b.cpp  
// compile with: /c  
#define TRUE 1  
```