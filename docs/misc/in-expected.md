---
title: "&#39;In&#39; attendu | Microsoft Docs"
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
  - "bc36607"
  - "vbc36607"
helpviewer_keywords: 
  - "BC36607"
ms.assetid: f390bca5-12fe-4fe1-bd86-7f8ab66dfbd8
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;In&#39; attendu
Une clause `From` ou `Aggregate` a été spécifiée sans l’opérateur `In`. Vous utilisez l’opérateur `In` pour identifier la collection à interroger.  
  
 **ID d’erreur :** BC36607  
  
### Pour corriger cette erreur  
  
1.  Ajoutez l’opérateur `In` et les champs clés à la clause `From` ou `Aggregate`. Voici un exemple :  
  
    ```vb#  
    Dim names = From pers In people Select pers.FirstName, pers.LastName  
    ```  
  
## Voir aussi  
 [From Clause](../Topic/From%20Clause%20\(Visual%20Basic\).md)   
 [Aggregate Clause](../Topic/Aggregate%20Clause%20\(Visual%20Basic\).md)   
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)