---
title: "Création d’un projet DLL MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfcdll.project
dev_langs:
- C++
helpviewer_keywords:
- MFC DLLs [MFC], creating projects
- DLLs [MFC], MFC
- projects [MFC], creating
- DLLs [MFC], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a7c040188db5caf46c0d58720320088967b59ea6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-mfc-dll-project"></a>Création d'un projet DLL MFC
Une DLL MFC est un fichier binaire qui agit comme une bibliothèque partagée de fonctions qui peuvent être utilisés simultanément par plusieurs applications. Pour créer un projet DLL MFC, le plus simple consiste à utiliser l’Assistant DLL MFC.  
  
> [!NOTE]
>  L’apparence des fonctionnalités dans l’IDE peut dépendre de vos paramètres actifs ou votre édition et peut-être différer de celles décrites dans l’aide. Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** . Pour plus d’informations, consultez [Personnalisation des paramètres de développement dans Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>Pour créer un projet de DLL MFC à l’aide de l’Assistant DLL MFC  
  
1.  Suivez les instructions de la rubrique d’aide [création d’un projet avec l’Assistant Application Visual C++](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
 **Remarque** dans les **nouveau projet** boîte de dialogue, sélectionnez le `MFC DLL` icône dans le volet Modèles pour ouvrir l’Assistant DLL MFC.  
  
1.  Définir les paramètres de votre application à l’aide de la [paramètres de l’application](../../mfc/reference/application-settings-mfc-dll-wizard.md) page de la [Assistant DLL MFC](../../mfc/reference/mfc-dll-wizard.md).  
  
    > [!NOTE]
    >  Ignorez cette étape afin que l'Assistant conserve les paramètres par défaut.  
  
2.  Cliquez sur **Terminer** pour fermer l’Assistant et ouvrir votre nouveau projet dans **l’Explorateur de solutions**.  
  
 Une fois votre projet créé, vous pouvez afficher les fichiers créés dans l’Explorateur de solutions. Pour plus d'informations sur les fichiers créés par l'Assistant pour votre projet, consultez le fichier Readme.txt généré pour le projet. Pour plus d’informations sur les types de fichiers, consultez [Types de fichiers créés pour les projets Visual C++](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Types de projet Visual C++](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)   
 [Ajout de fonctionnalités à l’aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Pages de propriétés](../../ide/property-pages-visual-cpp.md)   
 [Déploiement d’Applications](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)

