---
title: "Erreur du compilateur&#160;C2013 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2013"
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur&#160;C2013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\>' manquant  
  
 Il manque un signe supérieur de fermeture à une directive `#include`. Ajoutez le signe supérieur de fermeture pour corriger l’erreur.  
  
 L’exemple suivant génère l’erreur C2013 :  
  
```  
// C2013.cpp #include <stdio.h    // C2013  
```  
  
 Résolution possible :  
  
```  
// C2013b.cpp // compile with: /c #include <stdio.h>  
```