---
title: "Erreur du compilateur&#160;C2082 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2082"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2082"
ms.assetid: 87a6d442-157c-46e8-9bff-8388f8338ae0
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur&#160;C2082
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

redéfinition du paramètre formel 'identifier'  
  
 Un paramètre formel d’une fonction est redéclaré dans le corps de la fonction. Pour corriger l’erreur, supprimez la redéfinition.  
  
 L’exemple suivant génère l’erreur C2082 :  
  
```  
// C2082.cpp void func(int i) { int i;   // C2082 int ii;   // OK }  
```