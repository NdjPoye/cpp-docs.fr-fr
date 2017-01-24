---
title: "Erreur du compilateur C2194 | Microsoft Docs"
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
  - "C2194"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2194"
ms.assetid: df6e631c-0062-4844-9088-4cc7a0ff879f
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2194
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : segment texte  
  
 Le pragma `data_seg` utilise un nom de segment utilisé avec `code_seg`.  
  
 L'exemple suivant génère l'erreur C2194 :  
  
```  
// C2194.cpp  
// compile with: /c  
#pragma code_seg("MYCODE")  
#pragma data_seg("MYCODE")   // C2194  
#pragma data_seg("MYCODE2")   // OK  
```