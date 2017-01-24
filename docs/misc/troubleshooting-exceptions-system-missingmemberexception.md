---
title: "D&#233;pannage des exceptions&#160;: System.MissingMemberException | Microsoft Docs"
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
  - "MissingMemberException (classe)"
ms.assetid: c4cf497b-0554-47fe-b2e9-81ee3eb9ec04
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.MissingMemberException
Une exception <xref:System.MissingMemberException> est levée lors d'une tentative d'accès dynamique à un membre de classe qui n'existe pas.  
  
## Conseils associés  
 **Si un membre dans une bibliothèque de classes a été supprimé ou renommé, recompilez tous les assemblys qui font référence à la bibliothèque.**  
 Cette exception est généralement levée lorsqu'un champ ou une méthode est supprimé ou renommé dans un assembly et que la modification n'est pas répercutée dans un deuxième assembly qui tente d'accéder au membre manquant.  
  
 **Si vous tentez d'accéder à des membres sur une variable objet à liaison tardive, assurez\-vous qu'elle est déclarée comme variable membre Public.**  
 Les variables `Protected`, `Friend` et `Private` ne peuvent pas faire l'objet d'une liaison tardive en Visual Basic.  
  
## Voir aussi  
 <xref:System.MissingMemberException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)