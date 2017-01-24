---
title: "Fourniture de l&#39;aide contextuelle | Microsoft Docs"
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
  - "aide contextuelle"
  - "aide contextuelle, Assistant personnalisé"
  - "Assistants personnalisés, implémenter l'aide"
ms.assetid: c6c4d961-29d3-4d16-9f39-b12545aba540
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fourniture de l&#39;aide contextuelle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quand vous utilisez l'[Assistant personnalisé](../ide/application-settings-custom-wizard.md) pour créer un Assistant, celui\-ci insère un bouton **Aide** dans votre Assistant.  
  
 Chaque fichier .htm de votre projet inclut le code ci\-dessous de prise en charge du bouton **Aide** par votre Assistant.  
  
```  
<BUTTON CLASS="BUTTONS" ID="HelpBtn" ACCESSKEY="H"  
 onClick="window.external.OnHelp('vc.appwiz.custom.overview');">  
```  
  
 La <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.OnHelp%2A> spécifie le mot clé du fichier d'aide HTML associé à cette page de votre Assistant.  Pour plus d'informations sur la création de fichiers d'aide HTML à associer à la page, consultez [Page d'accueil de HTML Help](vsconhh1start).  Pour fournir l'aide correspondant à cette page de l'Assistant, vous devez remplacer la chaîne `'vc.appwiz.custom.overview'` par le mot clé qui identifie la rubrique d'aide HTML de la page.  
  
 **Remarque** Ce fichier .htm ne peut pas être intégré à l'aide MSDN compilée.  
  
## Voir aussi  
 [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md)   
 [Assistant personnalisé](../ide/custom-wizard.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)