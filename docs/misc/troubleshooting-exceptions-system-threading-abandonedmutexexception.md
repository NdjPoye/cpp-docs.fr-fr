---
title: "D&#233;pannage des exceptions&#160;: System.Threading.AbandonedMutexException | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "System.Threading.AbandonedMutexException (exception)"
  - "AbandonedMutexException (exception)"
ms.assetid: 11157066-32ed-492c-83af-29983f915eec
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.Threading.AbandonedMutexException
Exception levée si un thread attend sur un objet mutex et qu'un autre thread abandonne le mutex en sortant sans le libérer.  
  
## Notes  
 L'abandon d'un mutex indique en général une erreur sérieuse dans le code. Lorsqu'un thread sort sans libérer le mutex, les structures de données protégées par le mutex risquent de ne pas se trouver dans un état cohérent. Le thread suivant à demander la propriété du mutex peut gérer cette exception et continuer si l'intégrité des structures de données peut être vérifiée.  
  
## Voir aussi  
 <xref:System.Threading.AbandonedMutexException>   
 <xref:System.Threading.Mutex>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [Thread](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)