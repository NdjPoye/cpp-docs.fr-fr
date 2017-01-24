---
title: "D&#233;pannage des exceptions&#160;: System.TypeInitializationException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "TypeInitializationException (exception)"
  - "System.TypeInitializationException (exception)"
ms.assetid: c77e81fd-1518-49a1-8213-3f169658f5f5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.TypeInitializationException
Exception levée comme wrapper pour l'exception levée par l'initialiseur de classe.  
  
## Notes  
 Lorsqu'un initialiseur de classe ne réussit pas à initialiser un type, Lorsqu'un initialiseur de classe n'arrive pas à initialiser un type, une <xref:System.TypeInitializationException> est créée et passe une référence à l'exception levée par l'initialiseur de classe du type. La propriété <xref:System.Exception.InnerException%2A> de <xref:System.TypeInitializationException> contient l'exception sous\-jacente.  
  
## Voir aussi  
 <xref:System.TypeInitializationException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)