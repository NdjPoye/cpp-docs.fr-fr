---
title: "Avertissement du compilateur (niveau 1) C4616 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4616"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4616"
ms.assetid: 71e15265-c5bc-42ce-a6a9-4879892472b1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau 1) C4616
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma warning : le numéro d'avertissement 'numéro' n'est pas un avertissement de compilateur valide  
  
 Impossible de réassigner le numéro d'avertissement spécifié dans le pragma [warning](../../preprocessor/warning.md).  Le pragma a été ignoré.  
  
 L'exemple suivant génère l'erreur C4616 :  
  
```  
// C4616.cpp  
// compile with: /W1 /c  
#pragma warning( disable : 0 )   // C4616  
#pragma warning( disable : 999 )   // OK  
#pragma warning( disable : 4998 )   // OK  
```