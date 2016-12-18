---
title: "L’op&#233;rande &#39;TryCast&#39; doit &#234;tre un param&#232;tre de type contraint par classe, mais &#39;&lt;nom_param&#232;tre_type&gt;&#39; n’a pas de contrainte de classe | Microsoft Docs"
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
  - "BC30793"
  - "vbc30793"
helpviewer_keywords: 
  - "BC30793"
ms.assetid: a38a1da9-4413-4a69-a2ce-0b6d51c2c4ef
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# L’op&#233;rande &#39;TryCast&#39; doit &#234;tre un param&#232;tre de type contraint par classe, mais &#39;&lt;nom_param&#232;tre_type&gt;&#39; n’a pas de contrainte de classe
L’opérateur [TryCast Operator](../Topic/TryCast%20Operator%20\(Visual%20Basic\).md) est utilisé avec un opérande de paramètre de type qui n’est pas garanti d’être un type référence.  
  
 `TryCast` fonctionne uniquement sur les types référence, tels que les classes ou les interfaces. Quand vous passez un paramètre de type en tant qu’argument à `TryCast`, vous devez contraindre le paramètre de type à être un type référence. Pour cela, ajoutez un ou plusieurs des éléments suivants dans la liste des contraintes du paramètre de type :  
  
-   Un ou plusieurs noms d’interface \(l’argument de type doit tous les implémenter\)  
  
-   Au moins un nom de classe \(l’argument de type doit hériter de cette classe\)  
  
-   La contrainte [New Operator](../Topic/New%20Operator%20\(Visual%20Basic\).md) \(l’argument de type doit exposer un constructeur sans paramètre accessible par le code de création, et doit donc être une classe\)  
  
-   La contrainte [Class \(Visual Basic\)](http://msdn.microsoft.com/fr-fr/0777c6e6-46bc-451b-ad70-57b49d4ef4f7) \(l’argument de type doit être un type de référence\)  
  
 **ID d’erreur :** BC30793  
  
### Pour corriger cette erreur  
  
-   Si vous devez passer ce paramètre de type à `TryCast`, appliquez\-lui une ou plusieurs des contraintes de la liste précédente.  
  
-   Si vous ne pouvez pas exiger que le paramètre de type accepte uniquement un type référence, vous ne pourrez pas l’utiliser avec `TryCast`. Vous pourrez éventuellement utiliser la [CType, fonction](../Topic/CType%20Function%20\(Visual%20Basic\).md) à la place.  
  
## Voir aussi  
 [Types génériques Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)   
 [Widening and Narrowing Conversions](../Topic/Widening%20and%20Narrowing%20Conversions%20\(Visual%20Basic\).md)   
 [Implicit and Explicit Conversions](../Topic/Implicit%20and%20Explicit%20Conversions%20\(Visual%20Basic\).md)