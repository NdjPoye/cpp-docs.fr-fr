---
title: "La r&#233;solution de surcharge a &#233;chou&#233;, car aucun &#39;&lt;m&#233;thode&gt;&#39; accessible n’est plus sp&#233;cifique pour ces arguments&#160;: &lt;erreur&gt; | Microsoft Docs"
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
  - "bc30521"
  - "vbc30521"
helpviewer_keywords: 
  - "échec de la résolution"
  - "BC30521"
  - "échec de la résolution de surcharge"
ms.assetid: b8b41fa0-a64b-4e74-8443-be3afd2b6f11
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La r&#233;solution de surcharge a &#233;chou&#233;, car aucun &#39;&lt;m&#233;thode&gt;&#39; accessible n’est plus sp&#233;cifique pour ces arguments&#160;: &lt;erreur&gt;
Vous avez effectué un appel vers une méthode surchargée, mais le compilateur a trouvé au moins deux surcharges avec des listes de paramètres vers lesquelles votre liste d’arguments peut être convertie. Il ne peut donc pas opérer de sélection.  
  
 Le compilateur tente de faire correspondre les types de données dans la liste d’arguments appelante et la liste de paramètres de surcharge du mieux possible. Une conversion étendue de chacun de vos arguments en son paramètre correspondant est nécessaire, que le commutateur de vérification de type \([Option Strict Statement](../Topic/Option%20Strict%20Statement.md)\) soit `On` ou `Off`.  
  
 Si le compilateur trouve plusieurs surcharges qui satisfont au critère d’extension, il recherche ensuite la surcharge qui est la plus spécifique pour les types de données d’argument, c’est\-à\-dire celle qui appelle l’extension la moins importante. Il génère ce message d’erreur quand une surcharge est plus spécifique pour le type de données d’un argument alors qu’une autre surcharge est plus spécifique pour le type de données d’un autre argument. Pour plus d'informations et pour obtenir un exemple, consultez [Overload Resolution](../Topic/Overload%20Resolution%20\(Visual%20Basic\).md).  
  
 **ID d’erreur :** BC30521  
  
### Pour corriger cette erreur  
  
1.  Examinez toutes les surcharges pour la méthode et déterminez celle que vous souhaitez appeler.  
  
2.  Dans votre instruction appelante, faites correspondre les types de données des arguments aux types de données des paramètres définis pour la surcharge souhaitée. Vous devrez peut\-être utiliser [CType, fonction](../Topic/CType%20Function%20\(Visual%20Basic\).md) pour convertir un ou plusieurs types de données en types définis.  
  
## Voir aussi  
 [Procedure Overloading](../Topic/Procedure%20Overloading%20\(Visual%20Basic\).md)   
 [Considerations in Overloading Procedures](../Topic/Considerations%20in%20Overloading%20Procedures%20\(Visual%20Basic\).md)   
 [Overload Resolution](../Topic/Overload%20Resolution%20\(Visual%20Basic\).md)   
 [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md)   
 [Overloaded Properties and Methods](../Topic/Overloaded%20Properties%20and%20Methods%20\(Visual%20Basic\).md)   
 [Option Strict Statement](../Topic/Option%20Strict%20Statement.md)   
 [CType, fonction](../Topic/CType%20Function%20\(Visual%20Basic\).md)