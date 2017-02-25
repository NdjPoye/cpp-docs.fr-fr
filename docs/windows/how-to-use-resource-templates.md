---
title: "How to: Use Resource Templates | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "language-specific template files"
  - "resource templates"
  - "resources [Visual Studio], creating"
  - "rct files"
  - "templates, resource templates"
  - "resources [Visual Studio], templates"
  - ".rct files"
ms.assetid: bdfe7060-f98e-4859-8285-9c8570360e9d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# How to: Use Resource Templates
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un modèle de ressource est une ressource personnalisée que vous avez enregistrée en tant que fichier .rct.  Un modèle de ressource peut servir ensuite de point de départ pour la création d'autres ressources.  Les modèles de ressources permettent de gagner du temps pour le développement de ressources ou de groupes de ressources supplémentaires qui partagent des fonctionnalités, par exemple les contrôles standard et autres éléments récurrents.  Par exemple, vous pouvez être amené à inclure un bouton Aide et l'icône d'un logo d'entreprise dans plusieurs boîtes de dialogue.  Pour y parvenir rapidement, créez un modèle de boîte de dialogue, puis personnalisez\-le avec le logo et le bouton Aide.  
  
 Une fois que vous avez personnalisé le modèle de ressource, vous devez enregistrer vos changements dans le dossier de modèles \(ou un emplacement spécifié dans le chemin d'accès Include\) pour que le nouveau modèle de ressource apparaisse sous le type de ressource correspondant dans la [boîte de dialogue Ajouter une ressource](../windows/add-resource-dialog-box.md).  Vous pouvez ensuite utiliser le nouveau modèle de ressource aussi souvent que nécessaire.  
  
> [!NOTE]
>  Vous pouvez placer des fichiers modèles spécifiques aux langues dans les sous\-répertoires du répertoire de modèles principal.  Par exemple, vous pouvez placer les fichiers modèles anglais \(uniquement\) dans \\\<répertoire de modèles de ressources\>\\1033.  
  
### Pour créer un modèle pour des ressources  
  
1.  Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur votre projet.  
  
2.  Dans le menu contextuel, choisissez **Ajouter**, puis cliquez sur **Ajouter un nouvel élément**.  
  
3.  Dans la boîte de dialogue **Ajouter un nouvel élément**, dans le volet **Modèles**, choisissez **Fichier modèle de ressource \(.rct\)**.  
  
4.  Indiquez le nom et l'emplacement de votre nouveau fichier .rct, puis cliquez sur **Ouvrir**.  
  
5.  Le nouveau fichier .rct est ajouté à votre projet et apparaît dans l'Explorateur de solutions sous le dossier **Ressources**.  
  
     Double\-cliquez à présent sur le fichier .rct pour l'ouvrir dans une fenêtre de document, puis ajoutez\-lui des ressources \(cliquez avec le bouton droit sur le fichier dans la fenêtre de document et choisissez **Ajouter une ressource** dans le menu contextuel\).  Vous pouvez ensuite personnaliser ces ressources et enregistrer le fichier .rct.  
  
    > [!NOTE]
    >  Quand vous créez un fichier RCT, Visual Studio le recherche dans \\Program Files\\Microsoft Visual Studio 9.0\\VC\\VCResourceTemplates, dans \\Program Files\\Microsoft Visual Studio 9.0\\VC\\VCResourceTemplates\\*LCID* \(par exemple 1033 pour l'anglais\) *ou* dans le [chemin d'accès Include](../windows/how-to-specify-include-directories-for-resources.md).  Si vous préférez stocker vos fichiers RCT dans un autre dossier de fichiers, par exemple \\Mes documents, il vous suffit d'ajouter ce dossier dans le chemin d'accès Include, et Visual Studio le trouvera sans difficultés.  
  
### Pour convertir un fichier .rc existant en fichier .rct  
  
1.  [Ouvrez le fichier .rc en tant que fichier autonome](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
2.  Dans le menu **Fichier**, cliquez sur **Enregistrer \<*votre nom de fichier*\> sous**.  
  
3.  Spécifiez un emplacement, puis cliquez sur **OK**.  
  
### Pour créer une ressource à partir d'un modèle  
  
1.  Dans le volet [Affichage des ressources](../windows/resource-view-window.md), cliquez avec le bouton droit sur le fichier .rc, puis choisissez **Ajouter une ressource** dans le menu contextuel.  
  
2.  Dans la boîte de dialogue **Ajouter une ressource**, cliquez sur le signe plus \(**\+**\) en regard d'une ressource pour développer le nœud de la ressource et afficher tous les modèles disponibles.  
  
3.  Double\-cliquez sur le modèle à utiliser.  
  
4.  En fonction des besoins, modifiez la ressource ajoutée dans son éditeur de ressources.  
  
     L'éditeur de ressources fournit automatiquement un ID de ressource unique.  Vous pouvez réviser les [propriétés de la ressource](../windows/changing-the-properties-of-a-resource.md) en fonction des besoins.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.*  
  
 Spécifications  
  
 Win32  
  
## Voir aussi  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)