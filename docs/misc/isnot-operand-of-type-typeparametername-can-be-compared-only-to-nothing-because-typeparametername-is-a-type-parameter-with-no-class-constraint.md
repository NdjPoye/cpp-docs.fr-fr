---
title: "L’op&#233;rande &#39;IsNot&#39; de type &#39;&lt;nom_param&#232;tre_type&gt;&#39; peut uniquement &#234;tre compar&#233; &#224; &#39;Nothing&#39; car &#39;&lt;nom_param&#232;tre_type&gt;&#39; est un param&#232;tre de type sans contrainte de classe | Microsoft Docs"
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
  - "vbc32097"
  - "bc32097"
helpviewer_keywords: 
  - "BC32097"
ms.assetid: 50283a4b-70e3-4e59-9b9b-65e7cacf5ce1
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# L’op&#233;rande &#39;IsNot&#39; de type &#39;&lt;nom_param&#232;tre_type&gt;&#39; peut uniquement &#234;tre compar&#233; &#224; &#39;Nothing&#39; car &#39;&lt;nom_param&#232;tre_type&gt;&#39; est un param&#232;tre de type sans contrainte de classe
Un paramètre de type est utilisé en tant qu’opérande pour [IsNot Operator](../Topic/IsNot%20Operator%20\(Visual%20Basic\).md) quand il est défini sans mot clé [Classe \(Visual Basic\)](http://msdn.microsoft.com/fr-fr/0777c6e6-46bc-451b-ad70-57b49d4ef4f7) ou sans nom de classe spécifique dans sa liste de contraintes.  
  
 `IsNot` compare deux types référence pour déterminer s’ils pointent vers des instances d’objet différentes en mémoire. Il ne peut pas prendre un opérande qui n’est pas un type référence, sauf si l’autre opérande est [Nothing](../Topic/Nothing%20\(Visual%20Basic\).md).  
  
 **ID d’erreur :** BC32097  
  
### Pour corriger cette erreur  
  
-   Si vous pouvez exiger que l’argument de type fourni à ce paramètre de type soit toujours un type référence, ajoutez le mot clé `Class` ou un nom de classe spécifique à la liste de contraintes pour le paramètre de type.  
  
-   Si vous ne pouvez pas exiger que l’argument de type fourni à ce paramètre de type soit toujours un type référence, supprimez\-le de l’expression `IsNot`. Vous ne pouvez pas le comparer à d’autres types référence avec l’opérateur `IsNot`.  
  
## Voir aussi  
 [Types génériques Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)   
 [Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md)