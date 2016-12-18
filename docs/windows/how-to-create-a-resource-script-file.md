---
title: "How to: Create a Resource Script File | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "rc files, creating"
  - ".rc files, creating"
  - "resource script files, creating"
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Create a Resource Script File
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  L’Éditeur de ressources n’est pas disponible dans les éditions Express.  
>   
>  Ces informations s’appliquent aux applications de bureau Windows. Les projets dans les langages .NET n’utilisent pas de fichiers de script de ressources. Pour plus d’informations, consultez [Fichiers de ressources](../mfc/resource-files-visual-studio.md).  
  
### Pour créer un fichier de script de ressources \(.rc\)  
  
1.  Placez le focus sur le dossier de votre projet dans `Solution Explorer`, par exemple « MonProjet ».  
  
    > [!NOTE]
    >  Ne confondez pas le dossier du projet avec le dossier de solution dans l’Explorateur de solutions. Si vous placez le focus sur le dossier de solution, les choix disponibles dans la boîte de dialogue **Ajouter un nouvel élément** \(à l’étape 3\) seront différents.  
  
2.  Dans le menu **Projet**, cliquez sur **Ajouter un nouvel élément**.  
  
3.  Dans la boîte de dialogue **Ajouter un nouvel élément**, cliquez sur le dossier **Visual C\+\+**, puis choisissez **Fichier de ressources \(.rc\)** dans le volet droit.  
  
4.  Donnez un nom à votre fichier de script de ressources dans la zone de texte **Nom**, puis cliquez sur **Ouvrir**.  
  
 Vous pouvez maintenant [créer](../windows/how-to-create-a-resource.md) et ajouter de nouvelles ressources à votre fichier .rc.  
  
> [!NOTE]
>  Vous pouvez ajouter un script de ressources \(fichier .rc\) uniquement à un projet existant qui est chargé dans l’IDE de Visual Studio. Vous ne pouvez pas créer de fichier .rc autonome \(en dehors du projet\). Vous pouvez créer des [modèles de ressources](../windows/how-to-use-resource-templates.md) \(fichiers .rct\) à tout moment.  
  
 Configuration requise  
  
 Win32  
  
## Voir aussi  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)