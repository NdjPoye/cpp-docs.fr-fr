---
title: "MSBuild Error MSB3256 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSB3256"
ms.assetid: 809ccd0a-78cd-4bf5-83a8-2fb51815ea27
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3256
**MSB3256 : Aucun assembly n'a été lu depuis les listes de composants redistribuables.  Une liste d'exclusion du sous\-ensemble TargetFramework n'a pas pu être générée.**  
  
 Une liste d'éléments redistribuables \(liste de composants redistribuables\) n'a pas pu être trouvée.  
  
 Pour générer une liste d'assemblys à exclure du sous\-ensemble du .NET Framework, deux fichiers sont requis : une « liste de composants redistribuables » nommée FrameworkList.xml, qui contient les noms d'éléments redistribuables dans le .NET Framework, et une « liste de sous\-ensemble » nommée client.xml, qui contient les noms d'éléments dans le .NET Framework.  La définition de sous\-ensemble requiert les deux listes, si la liste de composants redistribuables est manquante, le sous\-ensemble du .NET Framework ne peut pas être ciblé.  
  
 Le [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)] est un sous\-ensemble de la bibliothèque runtime [!INCLUDE[net_v35_short](../misc/includes/net_v35_short_md.md)] complète.  Pour plus d'informations sur le [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)], consultez [.NET Framework Client Profile](../Topic/.NET%20Framework%20Client%20Profile.md).  
  
### Pour corriger cette erreur  
  
-   Fournissez une liste de composants redistribuables valide nommée FrameworkList.xml ou ciblez la bibliothèque redistribuable [!INCLUDE[net_v35_short](../misc/includes/net_v35_short_md.md)] complète.  Pour plus d'informations sur la façon de cibler le [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] complet, consultez [Comment : cibler une version du .NET Framework](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md).  
  
## Voir aussi  
 [Target Framework and Target Platform](../Topic/MSBuild%20Target%20Framework%20and%20Target%20Platform.md)   
 [Project Element \(MSBuild\)](../Topic/Project%20Element%20\(MSBuild\).md)   
 [Additional Resources](../Topic/Additional%20MSBuild%20Resources.md)