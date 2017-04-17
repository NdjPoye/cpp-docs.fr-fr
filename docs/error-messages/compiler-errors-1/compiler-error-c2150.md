---
title: "Erreur du compilateur C2150 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2150"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2150"
ms.assetid: 21e82a10-c1d4-4c0d-9dc6-c5d92ea42a31
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2150
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : un champ de bits doit être du type 'int', 'signed int' ou 'unsigned int'  
  
 Les champs de bits doivent être du type `int`, `signed` `int` ou `unsigned` `int`.  
  
 L’exemple suivant génère l’erreur C2150 :  
  
```  
// C2150.cpp // compile with: /c struct A { float a : 8;    // C2150 int i : 8;   // OK };  
```