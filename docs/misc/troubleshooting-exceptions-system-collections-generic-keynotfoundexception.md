---
title: "D&#233;pannage des exceptions&#160;: System.Collections.Generic.KeyNotFoundException | Microsoft Docs"
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
  - "KeyNotFoundException (classe)"
ms.assetid: de33f5bb-5709-46fe-b889-7105dbd24299
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.Collections.Generic.KeyNotFoundException
Une <xref:System.Collections.Generic.KeyNotFoundException> est levée lors d'une tentative de récupération d'une clé ou d'une paire clé\/valeur depuis une collection à l'aide d'une clé inexistante.  
  
## Conseils associés  
 **Vérifiez que la clé que vous utilisez existe dans la collection à laquelle vous tentez d'accéder.**  
 Cette exception se produit lorsqu'une opération tente de récupérer un élément dans une collection à l'aide d'une clé qui n'existe pas dans cette collection.  
  
### Notes  
 La méthode <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> peut être utilisée pour déterminer si une clé existe.  
  
## Voir aussi  
 <xref:System.Collections.Generic>   
 <xref:System.Collections.Generic.KeyNotFoundException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)