---
title: "L’op&#233;rande d’&#233;v&#233;nement d’instruction &#39;AddHandler&#39; ou &#39;RemoveHandler&#39; doit &#234;tre une expression qualifi&#233;e par un point ou un nom simple | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30677"
  - "bc30677"
helpviewer_keywords: 
  - "BC30677"
ms.assetid: b71eb2f0-0bb2-4aeb-94ec-5c37ab960d9e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# L’op&#233;rande d’&#233;v&#233;nement d’instruction &#39;AddHandler&#39; ou &#39;RemoveHandler&#39; doit &#234;tre une expression qualifi&#233;e par un point ou un nom simple
L’élément spécifié pour l’argument d’événement de `AddHandler` ou `RemoveHandler` n’est pas reconnu comme un événement.  
  
 **ID d’erreur :** BC30677  
  
### Pour corriger cette erreur  
  
-   Spécifiez le nom de l’objet qui déclenche l’événement suivi d’un point \(`.`\) et du nom de l’événement, comme dans l’exemple suivant.  
  
     [!code-vb[VbVbalrEventError#30](../misc/codesnippet/VisualBasic/addhandler-or-removehandler-statement-event-operand-must-be-a-dot-qualified-expression-or-a-simple-name_1.vb)]  
  
## Voir aussi  
 [AddHandler Statement](../Topic/AddHandler%20Statement.md)   
 [RemoveHandler Statement](../Topic/RemoveHandler%20Statement.md)   
 [NOT IN BUILD : AddHandler et RemoveHandler](http://msdn.microsoft.com/fr-fr/a7a24bd2-519a-46fe-8a2c-2b9df2ca28ef)   
 [Events](../Topic/Events%20\(Visual%20Basic\).md)