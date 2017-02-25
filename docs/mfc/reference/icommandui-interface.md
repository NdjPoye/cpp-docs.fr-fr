---
title: "ICommandUI Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ICommandUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandUI interface"
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# ICommandUI Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère les commandes d'interface utilisateur.  
  
## Syntaxe  
  
```  
interface class ICommandUI  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ICommandUI::Check](../Topic/ICommandUI::Check.md)|Définit l'élément d'interface utilisateur pour cette commande à l'état d'activation appropriée.|  
|[ICommandUI::ContinueRouting](../Topic/ICommandUI::ContinueRouting.md)|Indique le mécanisme de routage des commandes de continuer à router le message actuel vers le bas de la chaîne des gestionnaires.|  
|[ICommandUI::Enabled](../Topic/ICommandUI::Enabled.md)|Active ou désactive l'élément d'interface utilisateur pour cette commande.|  
|[ICommandUI::ID](../Topic/ICommandUI::ID.md)|Obtient l'ID de l'objet d'interface utilisateur représenté par l'objet d' `ICommandUI` .|  
|[ICommandUI::Index](../Topic/ICommandUI::Index.md)|Obtient l'index de l'objet d'interface utilisateur représenté par l'objet d' `ICommandUI` .|  
|[ICommandUI::Radio](../Topic/ICommandUI::Radio.md)|Définit l'élément d'interface utilisateur pour cette commande à l'état d'activation appropriée.|  
|[ICommandUI::Text](../Topic/ICommandUI::Text.md)|Définit le texte de l'élément d'interface utilisateur pour cette commande.|  
  
## Notes  
 Cette interface fournit les méthodes et les propriétés qui gèrent des commandes d'interface utilisateur.  `ICommandUI` est semblable à [CCmdUI Class](../../mfc/reference/ccmdui-class.md), sauf qu' `ICommandUI` est utilisé pour les applications MFC qui interagissent avec des composants.NET.  
  
 `ICommandUI` est utilisé dans un gestionnaire d' `ON_UPDATE_COMMAND_UI` dans [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)classe dérivée.  Lorsqu'un utilisateur d'une application active \(active ou cliquez sur\) un menu, chaque élément de menu est affiché comme activé ou désactivé.  La cible de chaque commande de menu fournit ces informations en implémentant un gestionnaire d' `ON_UPDATE_COMMAND_UI` .  Pour chacun des objets interface utilisateur de commande dans votre application, utilisez la fenêtre Propriétés pour créer une entrée de la table des messages et un prototype de fonction pour chaque gestionnaire.  
  
 Pour plus d'informations sur la façon dont l'interface d' `ICommandUI` aux commandes routage est utilisé, consultez [Comment : ajouter le routage des commandes au contrôle Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Pour plus d'informations sur l'utilisation de Windows Forms, consultez l' [Utilisation d'un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Pour plus d'informations sur la façon dont les commandes d'interface utilisateur sont gérées dans MFC, consultez [CCmdUI Class](../../mfc/reference/ccmdui-class.md).  
  
## Configuration requise  
 **en\-tête :** afxwinforms.h \(défini dans l'assembly atlmfc \\ lib \\ mfcmifc80.dll\)  
  
## Voir aussi  
 [CCmdUI Class](../../mfc/reference/ccmdui-class.md)