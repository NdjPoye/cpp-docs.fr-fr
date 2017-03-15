---
title: "Erreur du compilateur C2386 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2386"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2386"
ms.assetid: aaaa1284-34a0-4da2-8547-9fcbb559dae0
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C2386
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : un symbole avec ce nom existe déjà dans la portée actuelle  
  
 Vous avez essayé de créer un alias d’espace de noms, mais le nom que vous avez choisi existe déjà.  
  
 L’exemple suivant génère l’erreur C2386 :  
  
```  
// C2386.cpp namespace A { int k; } int i; namespace i = A;   // C2386, i already exists  
```