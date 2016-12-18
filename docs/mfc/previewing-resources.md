---
title: "Previewing Resources | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.resvw.resource.previewing"
  - "vs.resvw.resource.previewing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], viewing"
  - "resource previews"
  - "code, viewing"
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Previewing Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'aperçu des ressources vous permet d'afficher des ressources graphiques sans les ouvrir.  Cette fonctionnalité est également utile pour les exécutables, une fois ceux\-ci compilés, car les identificateurs de ressource se transforment en nombres.  Comme ces identificateurs numériques ne fournissent pas suffisamment d'informations, l'aperçu des ressources favorise leur identification.  
  
 Vous pouvez afficher un aperçu de la disposition visuelle des types de ressources suivants :  
  
-   Bitmap  
  
-   Boîte de dialogue  
  
-   Icône  
  
-   Menu  
  
-   Curseur  
  
-   Barre d'outils  
  
 La fonction d'aperçu visuel ne s'applique pas aux ressources d'accélérateur, de manifeste, de tables de chaîne et d'informations sur la version.  
  
### Pour avoir un aperçu des ressources  
  
1.  Dans l'[Affichage des ressources](../windows/resource-view-window.md) ou dans une fenêtre de document, sélectionnez votre ressource, par exemple, IDD\_ABOUTBOX.  
  
     **Remarque** Si votre projet ne contient pas déjà de fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dans la [fenêtre Propriétés](../Topic/Properties%20Window.md), cliquez sur le bouton **Pages de propriétés**.  
  
     \- ou \-  
  
3.  Dans le menu **Affichage**, cliquez sur **Pages de propriétés**.  
  
     La page de propriétés pour la ressource s'ouvre en affichant un aperçu de cette ressource.  Vous pouvez ensuite utiliser les touches Haut et Bas pour vous déplacer dans le contrôle Tree de l'Affichage des ressources ou la fenêtre de document.  La Page de propriétés reste ouverte et affiche toutes les ressources ayant le focus et susceptibles d'être prévisualisées.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Configuration requise**  
  
 Win32  
  
## Voir aussi  
 [How to: Open a Resource Script File Outside of a Project \(Standalone\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Resource Editors](../mfc/resource-editors.md)