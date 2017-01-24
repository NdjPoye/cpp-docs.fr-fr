---
title: "Option Strict On interdit les op&#233;randes de type Object pour l’op&#233;rateur &#39;&lt;nom_op&#233;rateur&gt;&#39; | Microsoft Docs"
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
  - "bc30038"
  - "vbc30038"
helpviewer_keywords: 
  - "BC30038"
ms.assetid: eb047d36-1fb4-460d-ae98-c76f31a89bed
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On interdit les op&#233;randes de type Object pour l’op&#233;rateur &#39;&lt;nom_op&#233;rateur&gt;&#39;
Les seuls opérateurs définis pour les variables objet sont `Is` et `TypeOf...Is`. Quand `Option Strict` a la valeur `On`, tous les opérandes doivent présenter les types de données définis pour l’opérateur donné.  
  
 **ID d’erreur :** BC30038  
  
### Pour corriger cette erreur  
  
-   Utilisez les fonctions de conversion de type appropriées, telles que `CInt` ou `CStr`, pour convertir les opérandes dans les types de données définis pour l’opérateur.  
  
## Voir aussi  
 [Is Operator](../Topic/Is%20Operator%20\(Visual%20Basic\).md)   
 [Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md)   
 [Type Conversion Functions](../Topic/Type%20Conversion%20Functions%20\(Visual%20Basic\).md)