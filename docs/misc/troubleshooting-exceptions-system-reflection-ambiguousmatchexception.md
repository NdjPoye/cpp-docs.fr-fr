---
title: "D&#233;pannage des exceptions&#160;: System.Reflection.AmbiguousMatchException | Microsoft Docs"
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
  - "System.Reflection.AmbiguousMatchException (exception)"
  - "AmbiguousMatchException (exception)"
ms.assetid: f92b5c51-42b6-4c2e-83df-0d598b3b41c4
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.Reflection.AmbiguousMatchException
Exception levée si, lors de la liaison à une méthode, plusieurs méthodes correspondent aux critères de liaison.  
  
## Notes  
 Une <xref:System.Reflection.AmbiguousMatchException> est levée si l'application appelle une classe sans pouvoir déterminer quelle classe ou classe surchargée utiliser. La liaison tente de localiser la classe à utiliser, déterminée par le nombre et le type des paramètres. Si elle trouve plusieurs classes acceptables, cette exception est levée.  
  
## Voir aussi  
 <xref:System.Reflection.AmbiguousMatchException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)