---
title: "D&#233;pannage des exceptions&#160;: System.NotCancelableException | Microsoft Docs"
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
  - "NotCancelableException (classe)"
ms.assetid: 36b82d4b-f075-4af5-993a-3e763a7e254a
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.NotCancelableException
Une `NotCancelableException` est levée lors d'une tentative d'annulation d'une opération non annulable.  
  
## Conseils associés  
 N'essayez pas d'annuler l'opération.  
 Certaines opérations ne peuvent pas être annulées et lèvent cette exception si vous tentez de le faire. Dans ce cas, évitez de fournir à l'utilisateur une option lui proposant d'annuler l'opération.  
  
## Voir aussi  
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)