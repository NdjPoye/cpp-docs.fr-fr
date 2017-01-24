---
title: "D&#233;pannage des exceptions&#160;: System.ArgumentNullException | Microsoft Docs"
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
  - "ArgumentNullException (classe)"
ms.assetid: 5f21413c-d997-47c6-9b06-3d85a719d51b
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.ArgumentNullException
Une exception <xref:System.ArgumentNullException> est levée lorsqu'une référence null \(`Nothing` en Visual Basic\) est passée à une méthode pour laquelle cet argument n'est pas valide.  
  
## Conseils associés  
 **Vérifiez les arguments pour vous assurer qu'ils ne sont pas null \(Nothing en Visual Basic\).**  
 Une référence null est une référence à un objet qui n'existe pas, généralement parce qu'aucune instance de l'objet n'a été créée par programme.  
  
## Notes  
 <xref:System.ArgumentNullException> se comporte de la même manière que <xref:System.ArgumentException>. Il permet au code de l'application de faire la différence entre les exceptions déclenchées par des arguments null et les exceptions déclenchées par des arguments non null. Pour des erreurs provoquées par des arguments non null, consultez [Dépannage des exceptions : System.ArgumentOutOfRangeException](../misc/troubleshooting-exceptions-system-argumentoutofrangeexception.md).  
  
## Voir aussi  
 <xref:System.ArgumentNullException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)