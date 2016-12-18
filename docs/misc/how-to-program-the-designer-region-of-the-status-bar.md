---
title: "Proc&#233;dure&#160;: programmation de la zone du concepteur de la barre d’&#233;tat | Microsoft Docs"
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
  - "zone du concepteur, barre d’état"
  - "barres d’état, programmation"
  - "barres d’état, zone du concepteur"
ms.assetid: 735a86bb-80b2-4557-9677-00799856017f
caps.latest.revision: 11
caps.handback.revision: 11
manager: "douge"
---
# Proc&#233;dure&#160;: programmation de la zone du concepteur de la barre d’&#233;tat
La zone du concepteur de la barre d'état de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] affiche des informations qui se rapportent à modifier, par exemple, le numéro de ligne ou le numéro de colonne de l'emplacement du curseur.  
  
### pour programmer la zone du concepteur de la barre d'état de Visual Studio  
  
1.  Obtenez une instance de l'interface d' <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar> , qui sont disponibles via le service d' <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> .  
  
2.  mettez à jour la zone du concepteur de la barre d'état en appelant la méthode d' <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.SetInsMode%2A> et la méthode d' <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.SetLineColChar%2A> d'instance d' <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar> .  
  
## Exemple  
 cet exemple montre comment programmer la zone du concepteur de la barre d'état.  
  
 [!code-vb[VSSDKDesignerStatusBar#1](../misc/codesnippet/VisualBasic/how-to-program-the-designer-region-of-the-status-bar_1.vb)]
 [!code-cs[VSSDKDesignerStatusBar#1](../misc/codesnippet/CSharp/how-to-program-the-designer-region-of-the-status-bar_1.cs)]  
  
## Voir aussi  
 [Extension de la barre d'état](../Topic/Extending%20the%20Status%20Bar.md)   
 [Comment : lire et écrire dans la zone de commentaires de la barre d’état](../misc/how-to-read-from-and-write-to-the-feedback-region-of-the-status-bar.md)   
 [Procédure : programmation de la région de barre de progression de la barre d’état](../misc/how-to-program-the-progress-bar-region-of-the-status-bar.md)   
 [Comment : utiliser la région d’animation de la barre d’état](../misc/how-to-use-the-animation-region-of-the-status-bar.md)