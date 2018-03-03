---
title: "Création d’un projet Makefile | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.makefile.project
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5e86bedbf83cd417cfc41317e5887304cda7ee76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-makefile-project"></a>Création d'un projet Makefile
Si vous avez un projet que vous générez à partir d'une ligne de commande avec un makefile, l'environnement de développement Visual Studio ne reconnaît pas votre projet. Pour ouvrir et générer votre projet en utilisant [!INCLUDE[vsUltShort](../ide/includes/vsultshort_md.md)], Visual Studio Professional ou Visual Studio Express pour Windows Desktop, tout d’abord créer un projet vide en sélectionnant le modèle de projet MakeFile. Vous pouvez ensuite utiliser ce projet pour générer votre projet à partir de l'environnement de développement Visual Studio.  
  
 Ce projet n'affiche aucun fichier dans l'Explorateur de solutions. Le projet spécifie les paramètres de génération, qui sont affichés dans la page de propriétés du projet.  
  
 Le fichier de sortie que vous spécifiez dans le projet n'a pas d'incidence sur le nom que le script génère ; il déclare uniquement une intention.  
  
### <a name="to-create-a-makefile-project"></a>Pour créer un projet Makefile  
  
1.  Suivez les instructions de la rubrique d’aide [création d’un projet avec l’Assistant Application Visual C++](../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
2.  Dans le **nouveau projet** boîte de dialogue, sélectionnez **projet Makefile** dans le volet Modèles pour ouvrir l’Assistant.  
  
3.  Dans le [paramètres de l’Application](../ide/application-settings-makefile-project-wizard.md) page fournissez la commande, sortie, nettoyer et régénérer les informations.  
  
4.  Cliquez sur **Terminer** pour fermer l’Assistant et ouvrir le projet nouvellement créé dans **l’Explorateur de solutions**.  
  
 Vous pouvez afficher et modifier les propriétés du projet dans sa page de propriétés. Consultez [définition des propriétés de projet Visual C++](../ide/working-with-project-properties.md) pour plus d’informations sur l’affichage de la page de propriétés.  
  
## <a name="see-also"></a>Voir aussi  
 [Assistant projet Makefile](../ide/makefile-project-wizard.md)   
 [Caractères spéciaux dans un Makefile](../build/special-characters-in-a-makefile.md)   
 [Contenu d’un makefile](../build/contents-of-a-makefile.md)