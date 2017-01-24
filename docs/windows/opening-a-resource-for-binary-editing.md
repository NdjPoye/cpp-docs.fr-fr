---
title: "Opening a Resource for Binary Editing | Microsoft Docs"
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
  - "vc.editors.binary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binary data, editing"
  - "resources [Visual Studio], opening for binary editing"
ms.assetid: d3cdb0e4-da66-410d-8e49-b29073ff2929
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Opening a Resource for Binary Editing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Pour ouvrir une ressource de bureau Windows pour l’édition binaire  
  
1.  Dans [Affichage des ressources](../windows/resource-view-window.md), sélectionnez le fichier de ressources que vous souhaitez modifier.  
  
    > [!NOTE]
    >  Si votre projet ne contient pas déjà un fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Cliquez avec le bouton droit sur la ressource et cliquez sur **Ouvrir au format binaire** dans le menu contextuel.  
  
    > [!NOTE]
    >  Si vous utilisez la fenêtre [Affichage des ressources](../windows/resource-view-window.md) pour ouvrir une ressource ayant un format que Visual Studio ne reconnaît pas \(comme RCDATA ou une ressource personnalisée\), la ressource s’ouvre automatiquement dans l’éditeur binaire.  
  
### Pour ouvrir une ressource managée pour l’édition binaire  
  
1.  Dans l’Explorateur de solutions, sélectionnez le fichier de ressources que vous souhaitez modifier.  
  
2.  Cliquez avec le bouton droit sur la ressource et choisissez **Ouvrir avec** dans le menu contextuel.  
  
3.  Dans la boîte de dialogue **Ouvrir avec**, sélectionnez **Éditeur binaire**.  
  
    > [!NOTE]
    >  Vous pouvez utiliser l’[éditeur d’images](../mfc/image-editor-for-icons.md) et l’[éditeur binaire](../mfc/binary-editor.md) pour travailler avec des fichiers de ressources dans des projets managés. Toutes les ressources managées que vous souhaitez modifier doivent être liées. Les éditeurs de ressources Visual Studio ne prennent pas en charge la modification des ressources incorporées.  
  
    > [!NOTE]
    >  Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 ![Éditeur binaire](../mfc/media/vcbinaryeditor2.png "vcBinaryEditor2")  
Données binaires pour une boîte de dialogue affichée dans l’éditeur binaire  
  
 Seules certaines valeurs ASCII sont représentées dans l’éditeur binaire \(0x20 à 0x7E\). Les caractères étendus sont affichés sous forme de points dans la section Valeur ASCII de l’éditeur binaire \(volet droit\). Les caractères « imprimables » sont les valeurs ASCII comprises entre 32 et 126.  
  
> [!NOTE]
>  Si vous souhaitez utiliser l’éditeur binaire sur une ressource déjà en cours de modification dans une autre fenêtre d’éditeur, fermez d’abord l’autre fenêtre d’éditeur.  
  
 **Spécifications**  
  
 Aucune  
  
## Voir aussi  
 [Binary Editor](../mfc/binary-editor.md)