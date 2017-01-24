---
title: "Op&#233;randes de type Object utilis&#233;s pour l’op&#233;rateur &#39;&lt;symbole_op&#233;rateur&gt;&#39;&#160;; utilisez l’op&#233;rateur &#39;IsNot&#39; pour tester l’identit&#233; de l’objet | Microsoft Docs"
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
  - "vbc42032"
  - "bc42032"
helpviewer_keywords: 
  - "BC42032"
ms.assetid: f43b163b-f8f6-489d-ba9e-df6398ccc553
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Op&#233;randes de type Object utilis&#233;s pour l’op&#233;rateur &#39;&lt;symbole_op&#233;rateur&gt;&#39;&#160;; utilisez l’op&#233;rateur &#39;IsNot&#39; pour tester l’identit&#233; de l’objet
Une expression utilise l’opérateur `<>` avec un ou deux opérandes du [Object Data Type](../Topic/Object%20Data%20Type.md).  
  
 Vous devez utiliser l’opérateur `Is` ou `IsNot` pour déterminer si deux références d’objet font référence à la même instance d’objet. Consultez « Comparaison d’objets » dans [Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md).  
  
 Quand une variable ou une expression prend la valeur `Object`, le compilateur doit exécuter une *liaison tardive*, ce qui entraîne des opérations supplémentaires au moment de l’exécution. Cela expose également votre application à des erreurs d’exécution potentielles. Par exemple, si vous attribuez un <xref:System.Windows.Forms.Form> à une variable `Object` et que vous essayez ensuite de l’utiliser avec l’opérateur `<>`, le runtime lève une <xref:System.InvalidCastException>, car Visual Basic ne peut pas convertir un objet <xref:System.Windows.Forms.Form> en un type de données qui convient à la comparaison de valeurs. Même si les deux opérandes prennent le type <xref:System.Windows.Forms.Form>, l’opération échoue, car `<>` n’est pas défini pour les opérandes <xref:System.Windows.Forms.Form>.  
  
 Par défaut, ce message est un avertissement. Pour plus d’informations sur le masquage des avertissements ou leur traitement en tant qu’erreurs, consultez [Configuration d'avertissements en Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **ID d’erreur :** BC42032  
  
### Pour corriger cette erreur  
  
-   Pour déterminer si deux références d’objet font référence à la même instance d’objet, utilisez l’opérateur `Is` ou `IsNot`.  
  
## Voir aussi  
 [Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md)   
 [IsNot Operator](../Topic/IsNot%20Operator%20\(Visual%20Basic\).md)   
 [How to: Determine Whether Two Objects Are Related](../Topic/How%20to:%20Determine%20Whether%20Two%20Objects%20Are%20Related%20\(Visual%20Basic\).md)   
 [How to: Determine Whether Two Objects Are Identical](../Topic/How%20to:%20Determine%20Whether%20Two%20Objects%20Are%20Identical%20\(Visual%20Basic\).md)