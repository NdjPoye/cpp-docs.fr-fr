---
title: "Annonce du suivi de s&#233;lection de la fen&#234;tre Propri&#233;t&#233;s | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "éditeurs (Kit de développement logiciel Visual Studio), support pages de propriétés"
  - "pages de propriétés, suivi de sélection"
  - "fenêtre Propriétés, suivi de sélection"
  - "sélection, suivi"
  - "éditeurs (Kit de développement logiciel Visual Studio), support fenêtre Propriétés"
ms.assetid: a7536f82-afd7-4894-9a60-84307fb92b7e
caps.latest.revision: 13
caps.handback.revision: 13
manager: "douge"
---
# Annonce du suivi de s&#233;lection de la fen&#234;tre Propri&#233;t&#233;s
Si vous souhaitez utiliser la fenêtre de **Propriétés** ou les pages de propriétés, par exemple, un formulaire, du texte, ou une sélection pour lequel vous souhaitez afficher les propriétés, vous devez avoir une connaissance complète de la façon dont vous et coordonnent la sélection.  Par exemple, vous devez savoir si vous avez une sélection unique ou les sélections multiples.  Vous devez ensuite annoncer votre type de sélection \(choisissez ou multiple\) à l'IDE à l'aide de l'interface d' <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection> .  Cette interface fournit les informations requises par la fenêtre de **Propriétés** .  
  
### pour annoncer la sélection à l'environnement  
  
1.  appel `QueryInterface` pour <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>.  
  
    1.  Pour ce faire, utilisez le pointeur de site passé à la vue lors de sa création.  
  
    2.  appelez `QueryService` de la vue pour le service d' `SID_STrackSelection` .  
  
         Retourne un pointeur vers <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection>.  
  
2.  Appelez la méthode d' <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> chaque fois que votre sélection change, puis passez un pointeur vers un objet qui implémente <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>.  
  
     L'objet conteneur de sélection peut utiliser choisissez ou multiple et contiennent des informations de sélection dans un objet d' `IDispatch` .  Appelant la méthode d' <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> notifie la fenêtre de **Propriétés** que la sélection a changé.  La fenêtre de **Propriétés** utilise ensuite les objets sur <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> pour déterminer si une sélection unique ou multiple se sont produits, et les sélections actives d'objet.  
  
     Si vous spécifiez une sélection multiple, la fenêtre de **Propriétés** trouve l'intersection entre les propriétés communes pour les objets.  Si vous spécifiez une sélection unique d'objet, la fenêtre de **Propriétés** affiche toutes les propriétés de l'objet.  
  
## Voir aussi  
 [Étendre les propriétés](../Topic/Extending%20Properties.md)   
 [Pages de propriétés](../Topic/Property%20Pages.md)