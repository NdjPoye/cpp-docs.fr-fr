---
title: "Files Affected by Resource Editing | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resource editing"
  - "resources [Visual Studio], editing"
ms.assetid: d0820df1-ba84-40ac-bce9-29ea5ee7e3f8
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Files Affected by Resource Editing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'environnement Visual Studio fonctionne avec les fichiers indiqués dans le tableau ci\-dessous pendant votre session de modification des ressources.  
  
|Nom de fichier|Description|  
|--------------------|-----------------|  
|Resource.h|Fichier d'en\-tête généré par l'environnement de développement. Il contient les définitions de symbole.|  
|Filename.aps|Version binaire du fichier de script de ressources actif. Ce fichier est utilisé pour le chargement rapide.<br /><br /> Les éditeurs de ressources ne lisent pas directement les fichiers .rc ou resource.h.  Le compilateur de ressources les compile en fichiers .aps, qui sont consommés par les éditeurs de ressources.  Ce fichier est une étape de compilation, qui stocke uniquement les données symboliques.  Comme pour un processus de compilation normal, les informations non symboliques \(par exemple les commentaires\) sont ignorées durant le processus de compilation.  Chaque fois que le fichier .aps n'est plus synchronisé au fichier .rc, le fichier .rc est régénéré \(par exemple, quand vous effectuez un enregistrement, l'éditeur de ressources remplace les fichiers .rc et resource.h\).  Les changements apportés aux ressources sont conservés dans le fichier .rc, mais les commentaires disparaissent une fois le fichier .rc remplacé.  Pour plus d'informations sur la conservation des commentaires, voir [Inclusion des ressources au moment de la compilation](../windows/how-to-include-resources-at-compile-time.md).|  
|.rc|Fichier de script de ressources qui contient le script des ressources de votre projet actif.  Ce fichier est remplacé par le fichier .aps à chaque enregistrement.|  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Spécifications  
 Win32  
  
## Voir aussi  
 [Resource Files](../mfc/resource-files-visual-studio.md)