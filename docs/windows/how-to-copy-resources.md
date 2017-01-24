---
title: "How to: Copy Resources | Microsoft Docs"
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
  - "vc.resvw.resource.copying"
  - "vs.resvw.resource.copying"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], moving between files"
  - "resources [Visual Studio], copying"
  - "resource files, copying or moving resources between"
  - "resource files, tiling"
  - ".rc files, copying resources between"
  - "rc files, copying resources between"
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Copy Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez copier des ressources d'un fichier à un autre sans les modifier ou vous pouvez [modifier la langue ou la condition d'une ressource lors de la copie](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md).  
  
 Il est très facile de copier des ressources à partir d'une ressource existante ou d'un fichier exécutable dans votre fichier de ressources.  Pour cela, ouvrez simultanément les deux fichiers qui contiennent les ressources et faites glisser les éléments d'un fichier à l'autre ou faites un copier\-coller entre les deux fichiers.  Cette méthode fonctionne pour les fichiers de script de ressources \(.rc\) et les fichiers modèles de ressources \(.rct\), de même que pour les fichiers exécutables \(.exe\).  
  
> [!NOTE]
>  Visual C\+\+ inclut des fichiers de ressources exemples que vous pouvez utiliser dans votre application.  Pour plus d'informations, consultez [CLIPART, exemple : ressources communes](http://msdn.microsoft.com/fr-fr/9bac2891-b6b3-49ec-a287-cec850c707e0).  
  
 Vous pouvez utiliser la méthode du glisser\-déplacer entre les fichiers .rc qui sont ouverts [en dehors du projet](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
### Pour copier des ressources entre des fichiers à l'aide du glisser\-déplacer  
  
1.  Ouvrez les deux fichiers de ressources autonomes \(pour plus d'informations, consultez [Ouverture d'un fichier de script de ressources en dehors d'un projet \(autonome\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)\).  Par exemple, ouvrez Source1.rc et Source2.rc.  
  
2.  Dans le premier fichier .rc, cliquez sur la ressource que vous souhaitez copier.  Par exemple, dans Source1.rc, cliquez sur IDD\_DIALOG1.  
  
3.  Maintenez la touche CTRL enfoncée tout en faisant glisser la ressource vers le second fichier .rc.  Par exemple, faites glisser IDD\_DIALOG1 de Source1.rc vers Source2.rc.  
  
    > [!NOTE]
    >  Si vous ne maintenez pas la touche CTRL enfoncée tout en faisant glisser la ressource, la ressource est déplacée et non copiée.  
  
### Pour copier des ressources à l'aide du copier\-coller  
  
1.  Ouvrez les deux fichiers de ressources autonomes \(pour plus d'informations, consultez [Ouverture d'un fichier de script de ressources en dehors d'un projet \(autonome\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)\).  Par exemple, Source1.rc et Source2.rc.  
  
2.  Dans le fichier source à partir duquel vous voulez copier une ressource \(par exemple, Source1.rc\), cliquez avec le bouton droit sur une ressource et sélectionnez **Copier** dans le menu contextuel.  
  
3.  Cliquez avec le bouton droit sur le fichier de ressources dans lequel vous voulez coller la ressource \(par exemple, Source2.rc\).  Dans le menu contextuel, sélectionnez **Coller**.  
  
    > [!NOTE]
    >  Vous ne pouvez pas effectuer un glisser\-déplacer ou un copier\-couper\-coller entre des fichiers de ressources du projet \(Affichage des ressources\) et des fichiers .rc autonomes \(ceux qui sont ouverts dans les fenêtres de document\).  Ces opérations étaient possibles dans les versions précédentes du produit.  
  
    > [!NOTE]
    >  Pour éviter les conflits avec les noms ou les valeurs de symboles du fichier existant, Visual C\+\+ peut modifier la valeur du symbole ou le nom et la valeur du symbole de la ressource transférée lorsque vous la copiez dans le nouveau fichier.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Configuration requise  
  
 Win32  
  
## Voir aussi  
 [How to: Open a Resource Script File Outside of a Project \(Standalone\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)