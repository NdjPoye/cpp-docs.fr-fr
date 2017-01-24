---
title: "Custom Controls in the Dialog Editor | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Custom Control"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [C++], templates"
  - "custom controls [Visual Studio], dialog boxes"
  - "custom controls [Visual Studio]"
  - "dialog box controls, custom (user) controls"
  - "Dialog editor, custom controls"
ms.assetid: f494b314-4000-4bbe-bbd0-4b18fb71ede1
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Custom Controls in the Dialog Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'Éditeur de boîtes de dialogue vous permet d'utiliser des contrôles existants « personnalisés » ou « utilisateur » dans une boîte de dialogue modèle.  
  
> [!NOTE]
>  Les contrôles personnalisés dans ce cas ne doivent pas être confondus avec les contrôles ActiveX.  Les contrôles ActiveX étaient parfois appelés contrôles personnalisés OLE.  Il ne faut également pas confondre ces contrôles avec des contrôles owner\-drawn dans Windows.  
  
 Cette fonctionnalité permet d'utiliser des contrôles autres que ceux qui sont fournis par Windows.  Au moment de l'exécution, le contrôle est associé à une classe de fenêtre \(différent d'une classe C\+\+\).  Vous pouvez effectuer la même tâche en installant un contrôle, par exemple un contrôle statique, dans votre boîte de dialogue.  Puis, au moment de l'exécution, dans la fonction [OnInitDialog](../Topic/CDialog::OnInitDialog.md), supprimez ce contrôle et remplacez\-le par votre contrôle personnalisé.  
  
 Il s'agit d'une vieille méthode.  Désormais, il est conseillé dans la plupart des cas d'écrire un contrôle ActiveX ou de sous\-classer un contrôle Windows commun.  
  
 Pour ces contrôles personnalisés, vous pouvez uniquement :  
  
-   Définir l'emplacement dans la boîte de dialogue.  
  
-   Taper une légende.  
  
-   Identifier le nom de la classe Windows du contrôle \(le code de votre application doit inscrire le contrôle par son nom\).  
  
-   Taper une valeur hexadécimale 32 bits qui définit le style du contrôle.  
  
-   Définir le style étendu.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Configuration requise  
 Win32  
  
## Voir aussi  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Contrôles](../mfc/controls-mfc.md)