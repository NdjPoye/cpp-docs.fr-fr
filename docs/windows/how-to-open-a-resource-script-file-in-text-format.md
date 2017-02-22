---
title: "How to: Open a Resource Script File in Text Format | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.resource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resource script files, opening in text format"
  - ".rc files, opening in text format"
  - "rc files, opening in text format"
ms.assetid: 0bc57527-f53b-40c9-99a9-4dcbc5c9af57
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# How to: Open a Resource Script File in Text Format
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Parfois, vous souhaitez afficher le contenu du fichier de script \(.rc\) de ressources de votre projet sans ouvrir une ressource, par exemple une boîte de dialogue, dans son éditeur de ressources spécifique.  Par exemple, vous souhaitez rechercher une chaîne dans toutes les boîtes de dialogue du fichier de ressources sans avoir à ouvrir chacune d'elles séparément.  
  
> [!NOTE]
>  Si votre projet ne contient pas déjà un fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
 Vous pouvez facilement ouvrir le fichier de ressources au format texte pour afficher toutes les ressources qu'il contient et effectuer des opérations globales prises en charge par l'[Éditeur de texte](http://msdn.microsoft.com/fr-fr/508e1f18-99d5-48ad-b5ad-d011b21c6ab1).  
  
> [!NOTE]
>  Les éditeurs de ressources ne lisent pas directement les fichiers .rc ou resource.h.  Le compilateur de ressources les compile en fichiers .aps, qui sont consommés par les éditeurs de ressources.  Ce fichier est une étape de compilation, qui stocke uniquement les données symboliques.  Comme pour un processus de compilation normal, les informations non symboliques \(par exemple les commentaires\) sont ignorées durant le processus de compilation.  Chaque fois que le fichier .aps n'est plus synchronisé au fichier .rc, le fichier .rc est régénéré \(par exemple, quand vous effectuez un enregistrement, l'éditeur de ressources remplace les fichiers .rc et resource.h\).  Les changements apportés aux ressources sont conservés dans le fichier .rc, mais les commentaires disparaissent une fois le fichier .rc remplacé.  Pour plus d'informations sur la conservation des commentaires, voir [Inclusion des ressources au moment de la compilation](../windows/how-to-include-resources-at-compile-time.md).  
  
### Pour ouvrir un fichier de script de ressources au format texte  
  
1.  Dans le menu **Fichier**, choisissez **Ouvrir**, puis cliquez sur **Fichier**.  
  
2.  Dans la boîte de dialogue **Ouvrir un fichier**, naviguez jusqu'au fichier de script de ressources à afficher au format texte.  
  
3.  Sélectionnez le fichier, puis cliquez sur la flèche déroulante vers le bas du bouton **Ouvrir** \(située à droite du bouton\).  
  
4.  Choisissez **Ouvrir avec** dans le menu déroulant.  
  
5.  Dans la boîte de dialogue **Ouvrir avec**, cliquez sur **Éditeur du code source \(texte\)**.  
  
6.  Dans la liste déroulante **Ouvrir en tant que**, sélectionnez **Texte**.  
  
     La ressource s'ouvre dans l'Éditeur de code source.  
  
 ou  
  
1.  Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le fichier .rc  
  
2.  Dans le menu contextuel, choisissez **Ouvrir avec**, puis sélectionnez **Éditeur du code source \(texte\)**.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Spécifications  
  
 Win32  
  
## Voir aussi  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)