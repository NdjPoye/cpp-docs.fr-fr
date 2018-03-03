---
title: Assistant Application Win32 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.win32.overview
dev_langs:
- C++
helpviewer_keywords:
- Win32 Application Wizard
- Win32 Project Wizard
ms.assetid: 5d7b3a5e-8461-479a-969a-67b7883725b9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c97caee74e1ae918924632802c155b23fffe0527
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="win32-application-wizard"></a>Application Win32 (Assistant)
L’Assistant Application Win32 Visual C++ vous permet de créer quatre types de projet possibles (répertoriés dans les en-têtes de colonne du tableau ci-dessous). Dans chaque cas, vous pouvez spécifier des options supplémentaires appropriées au type de projet que vous ouvrez. Le tableau suivant indique les options disponibles pour chaque type d’application.  
  
|Type de prise en charge|Application console|Application exécutable (Windows)|Bibliothèque de liens dynamiques|Bibliothèque statique|  
|---------------------|-------------------------|----------------------------------------|---------------------------|--------------------|  
|**Projet vide**|Oui|Oui|Oui|Non|  
|**Symboles d’exportation**|Non|Non|Oui|Non|  
|**En-tête précompilé**|Non|Non|Non|Oui|  
|**prise en charge ATL**|Oui|Non|Non|Non|  
|**prise en charge des MFC**|Oui|Non|Non|Oui|  
  
## <a name="overview"></a>Vue d'ensemble  
 La page de l’Assistant décrit les paramètres de projet actuels de l’application Win32 que vous créez. Par défaut, les options suivantes sont définies :  
  
-   Le projet est une application Windows.  
  
-   Le projet n’est pas vide.  
  
-   Le projet ne contient aucun symbole d’exportation.  
  
-   Le projet n’utilise pas de fichier d’en-tête précompilé (cette option est disponible pour les projets de bibliothèque statique uniquement).  
  
-   Le projet n’inclut pas la prise en charge de MFC ni d’ATL.  
  
 Pour changer ces valeurs par défaut, cliquez sur l’onglet [Paramètres de l’application](../windows/application-settings-win-32-project-wizard.md) dans la colonne gauche de l’Assistant, puis apportez les modifications souhaitées.  
  
 Une fois que vous avez créé une application de bureau Windows, vous pouvez ajouter des classes C++ génériques à l’aide de l’ [Assistant Classe C++ générique](../ide/generic-cpp-class-wizard.md) . Vous pouvez ajouter d’autres éléments, tels que des fichiers HTML, des fichiers d’en-tête, des ressources ou des fichiers texte.  
  
> [!NOTE]
>  Vous ne pouvez pas ajouter de classes ATL. En outre, vous ne pouvez ajouter de classes MFC qu’aux types d’application de bureau Windows qui prennent en charge MFC (consultez le tableau précédent).  
  
 Vous pouvez afficher les fichiers que l’Assistant a créés pour votre projet dans **l’Explorateur de solutions**. Pour plus d'informations sur les fichiers créés par l'Assistant pour votre projet, consultez le fichier Readme.txt généré pour le projet. Pour plus d’informations sur les types de fichier, consultez [Types de fichier créés pour les projets Visual C++](../ide/file-types-created-for-visual-cpp-projects.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Création d’une Application de bureau Windows vide](../windows/creating-an-empty-windows-desktop-application.md)   
 [Types de projets Visual C++](../ide/visual-cpp-project-types.md)