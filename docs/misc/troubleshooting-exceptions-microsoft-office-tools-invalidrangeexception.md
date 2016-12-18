---
title: "D&#233;pannage des exceptions&#160;: Microsoft.Office.Tools.InvalidRangeException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "Microsoft.Office.Tools.InvalidRangeException (exception)"
ms.assetid: 0deea25b-1152-40b6-89e2-e2e9c85f7dc0
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: Microsoft.Office.Tools.InvalidRangeException
Une exception <xref:Microsoft.Office.Tools.InvalidRangeException> est levée lorsque vous créez par programme un contrôle view dont la portée couvre plusieurs zones.  
  
## Conseils associés  
 Vérifiez que la zone couverte par la portée ne recoupe pas une autre portée.  
 Les portées ne peuvent pas se chevaucher.  
  
 Vérifiez, lorsque vous créez un contrôle view par programme, que vous n'incluez qu'une seule zone  
 -   Vérifiez, lorsque vous créez un contrôle view par programme, que vous n'incluez qu'une seule zone, autrement dit, que toutes les cellules sont rassemblées.  
  
## Voir aussi  
 <xref:Microsoft.Office.Tools.InvalidRangeException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)