---
title: "Erreur du compilateur C2149 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2149"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2149"
ms.assetid: 7a106dab-d79f-41b9-85be-f36e86e4d2ab
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2149
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : un champ de bits nommé ne peut pas avoir une largeur égale à zéro  
  
 Les champs de bits ne peuvent avoir une largeur égale à zéro que s’ils ne portent pas de nom.  
  
 L’exemple suivant génère l’erreur C2149 :  
  
```  
// C2149.cpp // compile with: /c struct C { int i : 0;   // C2149 int j : 2;   // OK };  
```