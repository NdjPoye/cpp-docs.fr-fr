---
title: "Erreur du compilateur C2008 | Microsoft Docs"
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
  - "C2008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2008"
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'caractère' : inattendu dans la définition d'une macro  
  
 Le caractère apparaît immédiatement après le nom de macro.  Pour corriger l'erreur, il doit y avoir un espace après le nom de macro.  
  
 L'exemple suivant génère l'erreur C2008 :  
  
```  
// C2008.cpp  
#define TEST1"mytest1"    // C2008  
```  
  
 Résolution possible :  
  
```  
// C2008b.cpp  
// compile with: /c  
#define TEST2 "mytest2"  
```