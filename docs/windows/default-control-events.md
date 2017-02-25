---
title: "Default Control Events | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dialog editor, default control events"
  - "controls [C++], default control events"
  - "events [C++], controls"
  - "dialog box controls, events"
ms.assetid: 75556b23-18f5-4390-97a4-2ecad3309741
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Default Control Events
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les noms de contrôle suivants sont accompagnés des événements par défaut :  
  
|Nom du contrôle|Événement par défaut|  
|---------------------|--------------------------|  
|Animate|**ACN\_START**|  
|Check Box|**BN\_CLICKED**|  
|Combo Box|**CBN\_SELCHANGE**|  
|Personnalisé|**TTN\_GETDISPINFO**|  
|Date Time Picker|**DTN\_DATETIMECHANGE**|  
|Zone d'édition|**EN\_CHANGE**|  
|Zone de groupe|\(Non applicable\)|  
|Hot key|**NM\_OUTOFMEMORY**|  
|Adresse IP|**IPN\_FIELDCHANGED**|  
|Liste|**LVN\_ITEMCHANGE**|  
|Zone de liste|**LBN\_SELCHANGE**|  
|Month calendar|**MCN\_SELCHANGE**|  
|Contrôle Picture|\(Non applicable\)|  
|Progression|**NM\_CUSTOMDRAW**|  
|Push button|**BN\_CLICKED**|  
|Radio Button|**BN\_CLICKED**|  
|RichEdit|**EN\_CHANGE**|  
|Scroll Bar|**NM\_THEMECHANGED**|  
|Slider|**NM\_CUSTOMDRAW**|  
|Spin|**UDN\_DELTAPOS**|  
|Static Text|\(Non applicable\)|  
|Onglet|**TCN\_SELCHANGE**|  
|Tree|**TVN\_SELCHANGE**|  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Configuration requise  
 Win32  
  
## Voir aussi  
 [Defining Member Variables for Dialog Controls](../mfc/defining-member-variables-for-dialog-controls.md)   
 [Types de messages associés aux objets interface utilisateur](../mfc/reference/message-types-associated-with-user-interface-objects.md)   
 [Modification d'un gestionnaire de messages](../mfc/reference/editing-a-message-handler.md)   
 [Définition d'un gestionnaire de messages pour un message réfléchi](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)   
 [Déclaration d'une variable basée sur votre nouvelle classe de contrôle](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)   
 [Substitution d'une fonction virtuelle](../ide/overriding-a-virtual-function-visual-cpp.md)