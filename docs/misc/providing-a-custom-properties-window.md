---
title: "Fourniture d’une fen&#234;tre de propri&#233;t&#233;s personnalis&#233;e | Microsoft Docs"
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
  - "navigateurs de propriétés, fourniture"
  - "fenêtre de propriétés, fourniture de votre propre fenêtre"
ms.assetid: 408dcdef-8ef9-4644-97d2-f311cd35824f
caps.latest.revision: 12
caps.handback.revision: 12
manager: "douge"
---
# Fourniture d’une fen&#234;tre de propri&#233;t&#233;s personnalis&#233;e
Il est possible de fournir votre propre fenêtre **Propriétés** pour un système de projet donné, au lieu d'étendre la fenêtre **Propriétés** fournie par l'environnement de développement intégré d' [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] \(IDE\).  Le scénario produit par le plus est lorsque vous implémentez vous\-même l'objet situé dans le frame de fenêtre.  
  
 En cas vous n'implémentez pas l'objet situé dans le frame de fenêtre, mais a toujours accès à celle\-ci par d'autres moyens, vous rencontrez plusieurs manières d'accéder à l'interface d' <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> comme indiqué dans la dernière procédure dans cette page.  
  
### Pour fournir votre fenêtre Propriétés  
  
1.  Définissez un GUID qui représente votre implémentation de fenêtre **Propriétés** .  
  
2.  Dans votre implémentation d' <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> , utilisez le service d' <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> pour offrir la fenêtre **Propriétés** en tant que service à l'environnement Visual Studio.  
  
### Pour appeler la fenêtre de propriétés  
  
1.  Appelez la méthode <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane.SetSite%2A>.  
  
2.  `QueryService` pour <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> d' <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> est passé à la méthode d' <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane.SetSite%2A> .  
  
3.  Obtenez <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx> de service d' <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> .  
  
4.  Appelez l' <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx.OnElementValueChange%2A> avec le premier paramètre a `SEID_PropertyBrowserSID` \(pris de l'énumération d' <xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID> \), et le troisième paramètre, `varValue`, qui représente une forme de chaîne du GUID qui représente votre fenêtre **Propriétés** .  Faites cet appel une seule fois à la première création de votre fenêtre de document fenêtre **Propriétés** .  Après l'appel cette fenêtre **Propriétés** est associée à votre frame de fenêtre.  
  
### Pour obtenir l'objet de frame de fenêtre lorsque vous n'êtes pas l'implémenteur  
  
-   Vous pouvez `QueryService` pour le service d' <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> d' <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> avec le paramètre `propid` défini à <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>.  
  
-   Vous pouvez obtenir la fenêtre de document actif par <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCurrentSelection%2A> appelant via le service de SVsMonitorSelection.  Définissez le paramètre `elementid` à `SEID_WindowFrame`, pris de l'énumération d' <xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID> .  
  
## Voir aussi  
 [Étendre les propriétés](../Topic/Extending%20Properties.md)   
 [Interfaces et les champs de la fenêtre Propriétés](../Topic/Properties%20Window%20Fields%20and%20Interfaces.md)