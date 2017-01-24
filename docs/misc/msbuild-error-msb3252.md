---
title: "Erreur MSBuild MSB3252 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSB3252"
helpviewer_keywords: 
  - "MSB3252"
ms.assetid: 4e6982b8-84b3-4d21-94e1-05cc10bf1393
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Erreur MSBuild MSB3252
**MSB3252 : Le projet a une référence au \<nom\> de l'assembly.  Cet assembly ne fait pas partie du .NET Framework Client Profile.  S'il n'a pas cette référence, des erreurs d'exécution ou de compilation peuvent se produire.**  
  
 Un appel a été passé à un membre d'un assembly ou d'un assembly dépendant qui ne fait pas partie du [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)].  Par conséquent, l'appel ne peut pas être résolu et l'application ne peut pas être compilée.  
  
 Pour plus d'informations sur le [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)], consultez [.NET Framework Client Profile](../Topic/.NET%20Framework%20Client%20Profile.md).  
  
### Pour corriger cette erreur  
  
-   Supprimez la référence d'assembly spécifiée de votre projet ou ciblez le [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] complet plutôt que la bibliothèque du sous\-ensemble [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)].  Pour plus d'informations sur la façon de cibler le [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] complet, consultez [Comment : cibler une version du .NET Framework](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md).  
  
## Voir aussi  
 [Target Framework and Target Platform](../Topic/MSBuild%20Target%20Framework%20and%20Target%20Platform.md)   
 [Project Element \(MSBuild\)](../Topic/Project%20Element%20\(MSBuild\).md)   
 [Additional Resources](../Topic/Additional%20MSBuild%20Resources.md)