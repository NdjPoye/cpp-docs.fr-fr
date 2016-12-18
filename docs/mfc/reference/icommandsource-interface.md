---
title: "ICommandSource Interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ICommandSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandSource interface"
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
caps.latest.revision: 24
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandSource Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère les commandes envoyées d'un objet source de la commande à un contrôle utilisateur.  
  
## Syntaxe  
  
```  
interface class ICommandSource  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ICommandSource::AddCommandHandler](../Topic/ICommandSource::AddCommandHandler.md)|Ajoute un gestionnaire de commandes à un objet source de la commande.|  
|[ICommandSource::AddCommandRangeHandler](../Topic/ICommandSource::AddCommandRangeHandler.md)|Ajoute un groupe de gestionnaires de commandes à un objet source de la commande.|  
|[ICommandSource::AddCommandRangeUIHandler](../Topic/ICommandSource::AddCommandRangeUIHandler.md)|Ajoute un groupe de gestionnaires de messages de commande d'interface utilisateur à un objet source de la commande.|  
|[ICommandSource::AddCommandUIHandler](../Topic/ICommandSource::AddCommandUIHandler.md)|Ajoute un gestionnaire de messages de commande d'interface utilisateur à un objet source de la commande.|  
|[ICommandSource::PostCommand](../Topic/ICommandSource::PostCommand.md)|Publie un message sans l'attendre à traiter.|  
|[ICommandSource::RemoveCommandHandler](../Topic/ICommandSource::RemoveCommandHandler.md)|Supprime un gestionnaire de commandes d'un objet source de la commande.|  
|[ICommandSource::RemoveCommandRangeHandler](../Topic/ICommandSource::RemoveCommandRangeHandler.md)|Supprime un groupe de gestionnaires de commandes d'un objet source de la commande.|  
|[ICommandSource::RemoveCommandRangeUIHandler](../Topic/ICommandSource::RemoveCommandRangeUIHandler.md)|Supprime un groupe de gestionnaires de messages de commande de l'interface utilisateur d'un objet source de la commande.|  
|[ICommandSource::RemoveCommandUIHandler](../Topic/ICommandSource::RemoveCommandUIHandler.md)|Supprime un gestionnaire de messages de commande de l'interface utilisateur d'un objet source de la commande.|  
|[ICommandSource::SendCommand](../Topic/ICommandSource::SendCommand.md)|Envoie un message et attend à traiter avant de retourner.|  
  
## Notes  
 Lorsque vous hébergez un contrôle utilisateur dans une vue MFC, [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md) route les commandes et les messages de la commande interface utilisateur de mise à jour du contrôle utilisateur pour lui permettre de gérer des commandes MFC \(par exemple, les éléments de menu de frame et des boutons de barre d'outils\).  En implémentant [ICommandTarget Interface](../../mfc/reference/icommandtarget-interface.md), vous attribuez au contrôle utilisateur une référence à l'objet d' `ICommandSource` .  
  
 Pour obtenir un exemple d'utilisation de `ICommandTarget`, consultez [Comment : ajouter le routage des commandes au contrôle Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Pour plus d'informations sur l'utilisation de Windows Forms, consultez l' [Utilisation d'un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## Configuration requise  
 **en\-tête :** afxwinforms.h \(défini dans l'assembly atlmfc \\ lib \\ mfcmifc80.dll\)  
  
## Voir aussi  
 [Comment : ajouter le routage des commandes au contrôle Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandTarget Interface](../../mfc/reference/icommandtarget-interface.md)