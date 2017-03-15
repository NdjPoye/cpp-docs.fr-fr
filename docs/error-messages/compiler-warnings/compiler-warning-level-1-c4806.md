---
title: "Avertissement du compilateur (niveau&#160;1) C4806 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4806"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4806"
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau&#160;1) C4806
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opération' : opération risquée : aucune valeur de type 'type' promue en type 'type' ne peut être égale à la constante donnée  
  
 Ce message fournit un avertissement contre le code tel que `b == 3`, où `b` est de type `bool`. Les règles de promotion entraînent la promotion de `bool` en `int`. Cela est légal, mais ne peut jamais être **true**. L’exemple suivant génère l’erreur C4806 :  
  
```  
// C4806.cpp // compile with: /W1 int main() { bool b = true; // try.. // int b = true; if (b == 3)   // C4806 { b = false; } }  
```