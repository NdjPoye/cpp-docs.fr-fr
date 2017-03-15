---
title: "How to: Import and Export Resources | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.resvw.resource.importing"
  - "vc.resvw.resource.importing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], exporting"
  - "graphics [C++], exporting"
  - "graphics [C++], importing"
  - "resources [Visual Studio], importing"
  - "bitmaps [C++], importing and exporting"
  - "toolbars [C++], importing"
  - "images [C++], importing"
  - "toolbars [C++], exporting"
  - "cursors [C++], importing and exporting"
  - "images [C++], exporting"
ms.assetid: 3c9329dc-dcb8-4edd-a600-78e3e572bd89
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# How to: Import and Export Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez importer des ressources graphiques \(images bitmap, icônes, curseurs et barres d'outils\), des fichiers HTML et des ressources personnalisées pour les utiliser dans Visual C\+\+.  Vous pouvez exporter les mêmes types de fichier depuis un projet Visual C\+\+ vers des fichiers distincts utilisables en dehors de l'environnement de développement.  
  
> [!NOTE]
>  Les types de ressource tels que les accélérateurs, les boîtes de dialogue et les tables de chaînes ne peuvent pas être importés ou exportés, car il ne s'agit pas de types de fichier autonomes.  
  
### Pour importer une ressource individuelle dans votre fichier de ressources actuel  
  
1.  Dans [Affichage des ressources](../windows/resource-view-window.md), cliquez avec le bouton droit sur le nœud du fichier de script de ressources \(\*.rc\) auquel vous souhaitez ajouter une ressource.  
  
2.  Dans le menu contextuel, cliquez sur **Importer**.  
  
3.  Recherchez et sélectionnez le nom de fichier de l'image bitmap \(.bmp\), de l'icône \(.ico\), du curseur \(.cur\), du fichier HTML \(.htm\), ou de tout autre fichier que vous souhaitez importer.  
  
4.  Cliquez sur **OK** pour ajouter la ressource au fichier sélectionné dans l'affichage **Ressources**.  
  
    > [!NOTE]
    >  Le processus d'importation fonctionne de la même façon, quel que soit le type de ressource que vous avez sélectionné.  La ressource importée est automatiquement ajoutée au nœud approprié pour ce type de ressource.  
  
### Pour exporter une image bitmap, une icône ou un curseur en tant que fichier distinct \(pour une utilisation en dehors de Visual C\+\+\)  
  
1.  Dans l'affichage **Ressources**, cliquez avec le bouton droit sur la ressource à exporter.  
  
2.  Dans le menu contextuel, cliquez sur **Exporter**.  
  
3.  Dans la boîte de dialogue **Exporter une ressource**, acceptez le nom de fichier actuel, ou tapez\-en un nouveau.  
  
4.  Accédez au dossier où vous souhaitez enregistrer le fichier, puis cliquez sur **Exporter**.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Spécifications  
  
 Win32  
  
## Voir aussi  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)