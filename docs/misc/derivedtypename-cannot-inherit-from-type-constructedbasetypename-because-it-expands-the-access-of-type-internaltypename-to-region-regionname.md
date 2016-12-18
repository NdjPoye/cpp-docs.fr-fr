---
title: "&#39;&lt;nom_type_d&#233;riv&#233;&gt;&#39; ne peut pas h&#233;riter de &lt;type&gt; &#39;&lt;nom_type_base_construit&gt;&#39;, car il &#233;tend l’acc&#232;s du type &#39;&lt;nom_type_interne&gt;&#39; &#224; &lt;r&#233;gion&gt; &#39;&lt;nom_r&#233;gion&gt;&#39; | Microsoft Docs"
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
  - "vbc30921"
  - "BC30921"
helpviewer_keywords: 
  - "BC30921"
ms.assetid: b0dd971a-80e2-4d37-925b-854d17411546
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;nom_type_d&#233;riv&#233;&gt;&#39; ne peut pas h&#233;riter de &lt;type&gt; &#39;&lt;nom_type_base_construit&gt;&#39;, car il &#233;tend l’acc&#232;s du type &#39;&lt;nom_type_interne&gt;&#39; &#224; &lt;r&#233;gion&gt; &#39;&lt;nom_r&#233;gion&gt;&#39;
Une classe ou une interface dérivée essaie d’étendre le niveau d’accès d’un type interne en l’utilisant comme argument de type dans une classe ou une interface de base.  
  
 Le code suivant peut générer cette erreur.  
  
```  
Public Class containingClass Public Class baseClass(Of t) End Class Friend Class derivedClass Inherits baseClass(Of internalStructure) End Class Private Structure internalStructure Dim firstMember As Integer End Structure End Class  
```  
  
 Le code à l’extérieur de `containingClass` n’est pas autorisé à accéder à `internalStructure`. Toutefois, `derivedClass` est accessible à partir de n’importe quel code dans le même assembly. Par conséquent, `derivedClass` ne peut pas hériter de `baseClass` s’il utilise `internalStructure` comme argument de type, car cela peut exposer `internalStructure` dans l’ensemble de la région de code de définition.  
  
 **ID d’erreur :** BC30921  
  
### Pour corriger cette erreur  
  
-   Modifiez les niveaux d’accès des classes ou des interfaces afin que le type dérivé n’étende pas le niveau d’accès du type interne.  
  
     ou  
  
-   Si vous ne pouvez pas modifier les niveaux d’accès, n’utilisez pas le type interne comme argument de type lors de la construction de la classe ou de l’interface de base.  
  
## Voir aussi  
 [Inherits Statement](../Topic/Inherits%20Statement.md)   
 [Inheritance Basics](../Topic/Inheritance%20Basics%20\(Visual%20Basic\).md)   
 [Access Levels in Visual Basic](../Topic/Access%20Levels%20in%20Visual%20Basic.md)   
 [Types génériques Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)