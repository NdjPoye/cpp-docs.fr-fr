---
title: "Gestion de la bo&#238;te &#224; outils | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Boîte à outils [Kit de développement logiciel Visual Studio], sélection automatique d’onglets"
  - "Boîte à outils [Kit de développement logiciel Visual Studio], gestion"
ms.assetid: 3b052047-f6db-46dd-b3bf-da1c348ee410
caps.latest.revision: 33
caps.handback.revision: 33
manager: "douge"
---
# Gestion de la bo&#238;te &#224; outils
Le [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)] permet à un VSPackage, tel qu’un éditeur ou un concepteur, de gérer l’appartenance et l’apparence de la **boîte à outils**.  
  
 De plus, la **boîte à outils** peut être gérée de manière automatisée. Pour plus d’informations sur la gestion d’une boîte à outils grâce à l’automatisation, consultez [Comment : contrôler la boîte à outils](../Topic/How%20to:%20Control%20the%20Toolbox.md).  
  
## Sélection automatique d’onglets dans la boîte à outils  
 Vous pouvez activer automatiquement un onglet ou une catégorie de la **boîte à outils** en fonction de l’éditeur ou du concepteur actuellement actif. Par exemple, si un concepteur de formulaires est activé, vous pouvez souhaiter sélectionner l’onglet **Tous les Windows Forms**.  
  
 Cette prise en charge est limitée aux éditeurs et concepteurs nécessitant ce qui suit :  
  
1.  L’implémentation d’un objet usine pour fournir des instances de l’éditeur ou du concepteur. Pour plus d’informations sur l’implémentation d’un objet usine pour un concepteur ou un éditeur, consultez [Fabriques d'éditeur](../Topic/Editor%20Factories.md).  
  
2.  Inscription de l’onglet de boîte à outils qui est activé automatiquement si l’éditeur ou le concepteur est ouvert.  
  
## Contrôle de la boîte à outils  
 En complément de la prise en charge de l’automatisation, le [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)] fournit les interfaces suivantes qui permettent aux VSPackages un plus grand contrôle sur la gestion de la **boîte à outils**.  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.Drawing.Design.IToolboxService>|Permet aux applications de gérer, ajouter et supprimer des objets <xref:System.Drawing.Design.ToolboxItem> à partir de la **boîte à outils**. Permet également la configuration de l’apparence et des catégories de la **boîte à outils**.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2>|Permet de gérer, ajouter et supprimer des contrôles ActiveX de la **boîte à outils**, ainsi que de configurer l’apparence et les catégories de la **boîte à outils**.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3>|Étend les fonctionnalités de <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> en fournissant une prise en charge complète pour la persistance et la localisation.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox4>||  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox5>||  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox6>||  
  
 Plusieurs points importants sont à prendre en compte quand vous utilisez ces interfaces :  
  
-   <xref:System.Drawing.Design.IToolboxService> est disponible uniquement pour les VSPackages MPF \(Managed Package Framework\).  
  
-   Les contrôles ne peuvent pas être ajoutés directement à la **boîte à outils** à l’aide de <xref:System.Drawing.Design.IToolboxService>.  
  
-   Un VSPackage doit utiliser <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> pour ajouter des contrôles ou héberger le contrôle dans un contrôle wrapper dérivé de <xref:System.Windows.Forms.AxHost>.  
  
     Visual Studio fournit l’outil `Aximp.exe` pour l’automatisation de l’encapsulation des contrôles ActiveX dans un contrôle dérivé de <xref:System.Windows.Forms.AxHost>. Pour plus d’informations, consultez [Aximp.exe \(Windows Forms ActiveX Control Importer\)](../Topic/Aximp.exe%20\(Windows%20Forms%20ActiveX%20Control%20Importer\).md).  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3> sont des interfaces COM disponibles via les assemblys PIA.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> dérive de <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox> et implémente toutes ses méthodes.  
  
     Les objets obtiennent uniquement une instance de <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2>.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3> ne dérive pas de <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> et n’implémente pas ses méthodes.  
  
     Les objets nécessitant des fonctionnalités dans les deux interfaces doivent obtenir des instances des deux interfaces depuis l’environnement.  
  
-   Quand vous utilisez <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3>, les informations concernant les noms canoniques \(non localisés\) des onglets sont gérées par les méthodes <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3.GetIDOfTab%2A> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3.SetIDOfTab%2A>.  
  
-   Quand vous utilisez <xref:System.Drawing.Design.IToolboxService>, c’est à l’implémenteur de gérer les informations localisées, telles que les noms des catégories.  
  
 Utilisez le mécanisme de paramètres pour permettre aux utilisateurs d’enregistrer les paramètres de la **boîte à outils** auxquels ils peuvent accéder à l’aide de la commande **Paramètres d’importation\/exportation**, située dans le menu **Outils** de l’IDE. Pour plus d’informations sur l’utilisation des paramètres, consultez [Options et paramètres d'extension utilisateur](../Topic/Extending%20User%20Settings%20and%20Options.md).  
  
## Voir aussi  
 [Extension de la boîte à outils](../misc/extending-the-toolbox.md)