---
title: "Application Win32 (Assistant) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.win32.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Application Win32 (Assistant)"
  - "Projet Win32 (Assistant)"
ms.assetid: 5d7b3a5e-8461-479a-969a-67b7883725b9
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Application Win32 (Assistant)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L’Assistant Application Win32 Visual C\+\+ vous permet de créer quatre types de projet possibles \(répertoriés dans les en\-têtes de colonne du tableau ci\-dessous\). Dans chaque cas, vous pouvez spécifier des options supplémentaires appropriées au type de projet que vous ouvrez. Le tableau suivant indique les options disponibles pour chaque type d’application.  
  
|Type de prise en charge|Application console|Application exécutable \(Windows\)|Bibliothèque de liens dynamiques|Bibliothèque statique|  
|-----------------------------|-------------------------|----------------------------------------|--------------------------------------|---------------------------|  
|**Projet vide**|Oui|Oui|Oui|Non|  
|**Symboles d’exportation**|Non|Non|Oui|Non|  
|**En\-tête précompilé**|Non|Non|Non|Oui|  
|**prise en charge ATL**|Oui|Non|Non|Non|  
|**prise en charge des MFC**|Oui|Non|Non|Oui|  
  
## Vue d'ensemble  
 La page de l’Assistant décrit les paramètres de projet actuels de l’application Win32 que vous créez. Par défaut, les options suivantes sont définies :  
  
-   Le projet est une application Windows.  
  
-   Le projet n’est pas vide.  
  
-   Le projet ne contient aucun symbole d’exportation.  
  
-   Le projet n’utilise pas de fichier d’en\-tête précompilé \(cette option est disponible pour les projets de bibliothèque statique uniquement\).  
  
-   Le projet n’inclut pas la prise en charge de MFC ni d’ATL.  
  
 Pour changer ces valeurs par défaut, cliquez sur l’onglet [Paramètres de l’application](../windows/application-settings-win-32-project-wizard.md) dans la colonne gauche de l’Assistant, puis apportez les modifications souhaitées.  
  
 Une fois que vous avez créé une application de bureau Windows, vous pouvez ajouter des classes C\+\+ génériques à l’aide de l’[Assistant Classe C\+\+ générique](../ide/generic-cpp-class-wizard.md). Vous pouvez ajouter d’autres éléments, tels que des fichiers HTML, des fichiers d’en\-tête, des ressources ou des fichiers texte.  
  
> [!NOTE]
>  Vous ne pouvez pas ajouter de classes ATL. En outre, vous ne pouvez ajouter de classes MFC qu’aux types d’application de bureau Windows qui prennent en charge MFC \(consultez le tableau précédent\).  
  
 Vous pouvez afficher les fichiers que l’Assistant a créés pour votre projet dans **l’Explorateur de solutions**. Pour plus d'informations sur les fichiers créés par l'Assistant pour votre projet, consultez le fichier Readme.txt généré pour le projet. Pour plus d’informations sur les types de fichier, consultez [Types de fichier créés pour les projets Visual C\+\+](../ide/file-types-created-for-visual-cpp-projects.md).  
  
## Voir aussi  
 [Création d’une application de bureau Windows vide](../windows/creating-an-empty-windows-desktop-application.md)   
 [Types de projets Visual C\+\+](../ide/visual-cpp-project-types.md)