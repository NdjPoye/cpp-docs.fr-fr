---
title: "Erreur du compilateur C2007 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2007"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2007"
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2007
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

syntaxe \#define  
  
 Aucun identificateur n'apparaît après un `#define`.  Pour corriger l'erreur, utilisez un identificateur.  
  
 L'exemple suivant génère l'erreur C2007 :  
  
```  
// C2007.cpp  
#define   // C2007  
```  
  
 Résolution possible :  
  
```  
// C2007b.cpp  
// compile with: /c  
#define true 1  
```