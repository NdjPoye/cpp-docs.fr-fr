---
title: "Erreur du compilateur C2383 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2383"
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Erreur du compilateur C2383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : les arguments par défaut ne sont pas autorisés sur ce symbole  
  
 Le compilateur C\+\+ n'autorise pas d'arguments par défaut pour les pointeurs fonction.  
  
 Ce code était accepté par le compilateur de la version précédente mais génère maintenant une erreur.  Pour obtenir un code compatible avec toutes les versions de Visual C\+\+, n'assignez pas de valeur par défaut à un argument pointeur fonction.  
  
 La ligne suivante génère l'erreur C2383 :  
  
```  
// C2383.cpp  
// compile with: /c   
void (*pf)(int = 0);   // C2383  
void (*pf)(int);   // OK  
```