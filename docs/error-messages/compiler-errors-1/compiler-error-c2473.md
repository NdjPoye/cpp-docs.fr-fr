---
title: "Erreur du compilateur&#160;C2473 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2473"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2473"
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur&#160;C2473
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : similaire à une définition de fonction, mais aucune liste de paramètres n’existe.  
  
 Le compilateur a détecté un élément qui ressemble à une fonction, sans liste de paramètres.  
  
## Exemple  
 L’exemple suivant génère l’erreur C2473.  
  
```  
// C2473.cpp // compile with: /clr /c class A { int i {}   // C2473 }; class B { int i() {}   // OK };  
```