---
title: "D&#233;pannage des exceptions&#160;: System.OperationCanceledException | Microsoft Docs"
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
  - "OperationCanceledException (classe)"
ms.assetid: 275e2887-7491-432b-9b80-a21bb794be29
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.OperationCanceledException
Une <xref:System.OperationCanceledException> est levée lors de l'exécution d'une opération si <xref:Microsoft.VisualBasic.FileIO.UICancelOption> a la valeur `ThrowException` et que l'opération est annulée.  
  
## Conseils associés  
 Si vous préférez que cette exception ne soit pas levée, affectez à <xref:System.OperationCanceledException> la valeur `DoNothing`.  
 La valeur par défaut de <xref:Microsoft.VisualBasic.FileIO.UICancelOption> est `ThrowException`. Si vous ne souhaitez pas cette exception soit levée lorsque l'utilisateur annule l'opération, affectez à l'énumération la valeur `DoNothing`.  
  
## Voir aussi  
 <xref:System.OperationCanceledException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)