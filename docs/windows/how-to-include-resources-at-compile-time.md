---
title: "How to: Include Resources at Compile Time | Microsoft Docs"
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
  - "vs.resvw.resource.including"
  - "vc.resvw.resource.including"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compiling source code, including resources"
  - "comments [C++], compiled files"
  - "resources [Visual Studio], including at compile time"
  - "projects [C++], including resources"
  - "#include directive"
  - "include directive (#include)"
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Include Resources at Compile Time
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Normalement, il est facile et pratique d'utiliser la disposition par défaut de toutes les ressources dans un seul fichier de script de ressources \(.rc\).  Toutefois, vous pouvez ajouter les ressources d'autres fichiers à votre projet actif au moment de la compilation en les répertoriant dans la zone **Directives au moment de la compilation** de la [boîte de dialogue Include des ressources](../windows/resource-includes-dialog-box.md).  
  
 Il existe plusieurs raisons qui justifient le placement des ressources dans un autre fichier que le fichier .rc principal :  
  
-   Vous souhaitez ajouter des commentaires à des instructions de ressource qui ne sont pas supprimées quand vous enregistrez le fichier .rc.  
  
     Les éditeurs de ressources ne lisent pas directement les fichiers .rc ou resource.h.  Le compilateur de ressources les compile en fichiers .aps, qui sont consommés par les éditeurs de ressources.  Ce fichier est une étape de compilation, qui stocke uniquement les données symboliques.  Comme pour un processus de compilation normal, les informations non symboliques \(par exemple les commentaires\) sont ignorées durant le processus de compilation.  Chaque fois que le fichier .aps n'est plus synchronisé au fichier .rc, le fichier .rc est régénéré \(par exemple, quand vous effectuez un enregistrement, l'éditeur de ressources remplace les fichiers .rc et resource.h\).  Les changements apportés aux ressources sont conservés dans le fichier .rc, mais les commentaires disparaissent une fois le fichier .rc remplacé.  
  
-   Vous souhaitez inclure des ressources qui ont déjà été développées et testées, et qui n'ont pas besoin de modifications supplémentaires.  \(Les fichiers inclus mais dépourvus d'extension .rc ne sont pas modifiables par les éditeurs de ressources.\)  
  
-   Vous souhaitez inclure des ressources utilisées par plusieurs projets différents, ou qui font partie d'un système de contrôle de version du code source et qui doivent donc exister dans un emplacement central où les modifications affectent tous les projets.  
  
-   Vous souhaitez inclure des ressources \(par exemple des ressources RCDATA\) qui ont un format personnalisé.  Les ressources RCDATA peuvent avoir des spécifications particulières.  Par exemple, vous ne pouvez pas utiliser une expression en tant que valeur pour le champ nameID.  Pour plus d'informations, voir la documentation du [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  
  
 Si vos fichiers .rc existants comportent des sections qui répondent à ces conditions, placez ces sections dans un ou plusieurs fichiers .rc distincts, puis incluez\-les dans votre projet via la [boîte de dialogue Include des ressources](../windows/resource-includes-dialog-box.md).  Le fichier *NomProjet*.rc2 créé dans le sous\-répertoire \\res d'un nouveau projet est utilisé à cet effet.  
  
### Pour inclure des ressources dans votre projet au moment de la compilation  
  
1.  Placez les ressources dans un fichier de script de ressources portant un nom de fichier unique.  N'utilisez pas *NomProjet*.rc, car il s'agit du nom de fichier utilisé pour le fichier de script de ressources principal.  
  
2.  Cliquez avec le bouton droit sur le fichier .rc \(dans [Affichage des ressources](../windows/resource-view-window.md)\), puis choisissez **Include des ressources** dans le menu contextuel.  
  
3.  Dans la zone **Directives au moment de la compilation**, ajoutez la directive de compilateur [\#include](../preprocessor/hash-include-directive-c-cpp.md) pour inclure le nouveau fichier de ressources dans le fichier de ressources principal de l'environnement de développement.  
  
     Les ressources des fichiers inclus de cette façon sont intégrées à votre fichier exécutable au moment de la compilation.  Elles ne sont pas directement modifiables quand vous travaillez sur le fichier .rc principal de votre projet.  Vous devez ouvrir les fichiers .rc inclus séparément.  Les fichiers inclus mais dépourvus d'extension .rc ne sont pas modifiables par les éditeurs de ressources.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Spécifications  
  
 Win32  
  
## Voir aussi  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)