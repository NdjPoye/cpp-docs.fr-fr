---
title: "Include des ressources, bo&#238;te de dialogue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.resourceincludes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Include des ressources (boîte de dialogue)"
  - "fichiers rc, modification du stockage"
  - "fichiers d’en-tête de symbole, modification"
  - "compilation de code source, ressources comprises"
  - "fichiers .rc, modification du stockage"
  - "fichiers d’en-tête de symbole, lecture seule"
  - "symboles, fichiers d’en-tête de symbole"
ms.assetid: 659a54e6-e416-4045-8411-798730ff4ce3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Include des ressources, bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser la boîte de dialogue **Include des ressources** pour modifier la disposition de travail classique de l'environnement en matière de stockage de toutes les ressources du fichier .rc du projet, et de tous les [symboles](../mfc/symbols-resource-identifiers.md) de Resource.h.  
  
 Pour ouvrir la boîte de dialogue **Include des ressources**, cliquez avec le bouton droit sur un fichier .rc dans [Affichage des ressources](../windows/resource-view-window.md), puis choisissez **Include des ressources** dans le menu contextuel.  
  
 **Fichier d'en\-tête de symbole**  
 Vous permet de modifier le nom du fichier d'en\-tête où sont stockées les définitions de symbole de votre fichier de ressources.  Pour plus d'informations, voir [Modification des noms des fichiers d'en\-tête de symbole](../windows/changing-the-names-of-symbol-header-files.md).  
  
 **Directives de symboles en lecture seule**  
 Vous permet d'inclure les fichiers d'en\-tête qui contiennent les symboles à ne pas modifier durant une session d'édition.  Par exemple, vous pouvez inclure un fichier de symboles partagé entre plusieurs projets.  Vous pouvez également inclure des fichiers MFC .h.  Pour plus d'informations, voir [Ajout de symboles partagés \(lecture seule\) ou calculés](../windows/including-shared-read-only-or-calculated-symbols.md).  
  
 **Directives de compilation**  
 Vous permet d'inclure des fichiers de ressources qui sont créés et modifiés à l'écart des ressources de votre fichier de ressources principal, qui contiennent des directives de compilation \(comme celles qui incluent des ressources de manière conditionnelle\) ou qui contiennent des ressources dans un format personnalisé.  Vous pouvez également utiliser la zone Directives de compilation pour inclure des fichiers de ressources MFC standard.  Pour plus d'informations, voir [Inclusion de ressources au moment de la compilation](../windows/how-to-include-resources-at-compile-time.md).  
  
> [!NOTE]
>  Les entrées de ces zones de texte apparaissent dans le fichier .rc marqué par  `TEXTINCLUDE 1`, `TEXTINCLUDE 2` et `TEXTINCLUDE 3`, respectivement.  Pour plus d'informations, voir [TN035 : utilisation de plusieurs fichiers de ressources et fichiers d'en\-tête avec Visual C\+\+](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).  
  
 Une fois que vous avez apporté des changements à votre fichier de ressources via la boîte de dialogue **Include des ressources**, vous devez fermer le fichier .rc, puis le rouvrir pour que les changements prennent effet.  Pour plus d'informations, voir [Inclusion de ressources au moment de la compilation](../windows/how-to-include-resources-at-compile-time.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Spécifications  
 Win32  
  
## Voir aussi  
 [How to: Specify Include Directories for Resources](../windows/how-to-specify-include-directories-for-resources.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)