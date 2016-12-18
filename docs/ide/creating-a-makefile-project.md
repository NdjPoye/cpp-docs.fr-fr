---
title: "Cr&#233;ation d&#39;un projet Makefile | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.makefile.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "projets Makefile, créer"
  - "fichiers projet (C++), projets Makefile"
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;un projet Makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous avez un projet que vous générez à partir d'une ligne de commande avec un makefile, l'environnement de développement Visual Studio ne reconnaît pas votre projet.  Pour ouvrir et générer votre projet à l'aide de [!INCLUDE[vsUltShort](../ide/includes/vsultshort_md.md)], [!INCLUDE[vsPro](../ide/includes/vspro_md.md)] ou de Visual Studio Express pour Windows Desktop, créez d'abord un projet vide en sélectionnant le modèle de projet Makefile.  Vous pouvez ensuite utiliser ce projet pour générer votre projet à partir de l'environnement de développement Visual Studio.  
  
 Ce projet n'affiche aucun fichier dans l'Explorateur de solutions.  Le projet spécifie les paramètres de génération, qui sont affichés dans la page de propriétés du projet.  
  
 Le fichier de sortie que vous spécifiez dans le projet n'a pas d'incidence sur le nom que le script génère ; il déclare uniquement une intention.  
  
### Pour créer un projet Makefile  
  
1.  Suivez les instructions de la rubrique d'aide [Création d'un projet à l'aide d'un Assistant Application Visual C\+\+](../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
2.  Dans la boîte de dialogue **Nouveau projet**, sélectionnez **Projet Makefile** dans le volet Modèles pour ouvrir l'Assistant.  
  
3.  Dans la page [Paramètres de l'application](../ide/application-settings-makefile-project-wizard.md), indiquez les informations relatives à la ligne de commande, la sortie, le nettoyage et la régénération.  
  
4.  Cliquez sur **Terminer** pour fermer l'Assistant et ouvrir le nouveau projet créé dans l'**Explorateur de solutions**.  
  
 Vous pouvez afficher et modifier les propriétés du projet dans sa page de propriétés.  Consultez [Définition des propriétés de projets Visual C\+\+](../ide/working-with-project-properties.md) pour obtenir des informations sur l'affichage d'une page de propriétés.  
  
## Voir aussi  
 [Projet Makefile \(Assistant\)](../ide/makefile-project-wizard.md)   
 [Caractères spéciaux dans un makefile](../build/special-characters-in-a-makefile.md)   
 [Contenu d'un makefile](../build/contents-of-a-makefile.md)