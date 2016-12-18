---
title: "Conception d&#39;un Assistant | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistants personnalisés (C++), concevoir des projets"
  - "projets (C++), Assistants personnalisés"
  - "projets Visual C++, Assistants personnalisés"
  - "Assistants (C++), personnalisé"
ms.assetid: a7c0be7e-9297-4fed-83e3-5645c896d56b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conception d&#39;un Assistant
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il peut être nécessaire de créer des projets à fonctionnalités standard différentes de celles des Assistants Application fournis en Visual C\+\+.  Pour ces tâches, vous pouvez utiliser l'architecture de l'Assistant Visual C\+\+, conçue pour faciliter l'extensibilité et la personnalisation.  Vous pouvez créer un Assistant à l'aide de l'[Assistant personnalisé Visual C\+\+](../ide/creating-a-custom-wizard.md).  Après création de cet Assistant, il est possible de le configurer pour générer les fichiers de départ nécessaires à vos projets.  
  
 Un Assistant Visual C\+\+ est un contrôle HTML.  Il utilise le moteur de l'Assistant Visual C\+\+, <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI>, qui fournit des services communs, comme <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI.NavigateToCommandHandler%2A>, <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI.OkCancelAlert%2A> et autres.  L'Assistant utilise aussi le moteur de script, qui lui permet de comprendre à la fois VBScript et [JScript .NET](http://msdn.microsoft.com/fr-fr/c7e636ee-c10f-45b1-85ec-fe2daca30bf5).  
  
 L'architecture d'Assistant permet d'accéder directement aux modèles objet suivants, pour appeler leurs méthodes, leurs propriétés et événements depuis JScript ou les fichiers HTML.  \(Pour plus d'informations, consultez les exemples qui se trouvent dans [Les fichiers HTML](../ide/html-files.md) et [Le fichier JScript](../ide/jscript-file.md).\)  
  
-   [Modèle objet DTE \(Developer Tools Environment\)](../Topic/Extending%20the%20Visual%20Studio%20Environment.md)  
  
-   [Modèle de code Visual C\+\+](http://msdn.microsoft.com/fr-fr/dd6452c2-1054-44a1-b0eb-639a94a1216b)  
  
-   [Modèle de projet Visual C\+\+](http://msdn.microsoft.com/fr-fr/06c1bbd9-4c79-4f97-ad6d-2b1dea8ecd1f)  
  
-   [Modèle d'Assistant Visual C\+\+](http://msdn.microsoft.com/fr-fr/159395ac-33c7-47bf-ad42-4e1435ddc758)  
  
 Consultez [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md) pour une description de chaque élément de la conception d'un Assistant.  
  
## Voir aussi  
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Étapes de conception d'un Assistant](../ide/steps-to-designing-a-wizard.md)   
 [Personnalisation de votre Assistant](../ide/customizing-your-wizard.md)