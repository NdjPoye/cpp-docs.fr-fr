---
title: "D&#233;pannage des exceptions&#160;: System.ServiceModel.ServiceActivationException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ServiceActivationException (exception)"
  - "System.ServiceModel.ServiceActivationException (exception)"
ms.assetid: 32a3ea87-d6da-40bf-ba04-e862ac122391
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.ServiceModel.ServiceActivationException
Une exception <xref:System.ServiceModel.ServiceActivationException> est renvoyée en cas d'échec lors de l'activation d'un service.  
  
## Notes  
 Cette exception dérive de <xref:System.ServiceModel.CommunicationException>, qui représente une classe d'erreurs récupérables susceptibles d'être renvoyées pendant la communication entre des points de terminaison et les applications clientes et de service [!INCLUDE[vsindigo](../misc/includes/vsindigo_md.md)] fiables qui doivent être gérées. Pour empêcher le gestionnaire <xref:System.ServiceModel.CommunicationException> plus générique d'intercepter le <xref:System.ServiceModel.ActionNotSupportedException> plus spécifique, interceptez cette exception avant de gérer <xref:System.ServiceModel.CommunicationException>.  
  
## Voir aussi  
 <xref:System.ServiceModel.ServiceActivationException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)