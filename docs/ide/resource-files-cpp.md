---
title: "Fichiers de ressources (C++) | Microsoft Docs"
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
  - "types de fichiers (C++), fichiers de ressources"
  - "fichiers de ressources"
  - "ressources (C++)"
ms.assetid: 338a4a0f-0c62-4ef1-a34f-5d86262d93a4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fichiers de ressources (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les ressources sont des éléments d'interface qui fournissent des informations à l'utilisateur.  Les bitmaps, les icônes, les barres d'outils et les curseurs sont tous des ressources.  Certaines ressources peuvent être manipulées afin d'effectuer une action spécifique, telle que sélectionner une commande dans un menu ou entrer des données dans une boîte de dialogue.  
  
 Pour plus d'informations, consultez [Utilisation de ressources](../mfc/working-with-resource-files.md).  
  
|Nom du fichier|Emplacement dans les répertoires|Emplacement dans l'Explorateur de solutions|Description|  
|--------------------|--------------------------------------|-------------------------------------------------|-----------------|  
|*Nomprojet*.rc|*Nomprojet*|Fichiers sources|Fichier de script de ressources pour le projet.  Ce fichier contient les éléments suivants, selon le type du projet et la prise en charge sélectionnée pour le projet \(par exemple, barres d'outils, boîtes de dialogue ou HTML\) :<br /><br /> -   Définition du menu par défaut.<br />-   Tables d'accélérateurs et de chaînes.<br />-   Boîte de dialogue **À propos de** par défaut.<br />-   Autres boîtes de dialogue.<br />-   Fichier icône \(res\\*Nomprojet*.ico\).<br />-   Informations de version.<br />-   Bitmaps.<br />-   Barre d'outils.<br />-   Fichiers HTML.<br /><br /> Le fichier de ressources inclut le fichier Afxres.rc pour les ressources standard des classes MFC \(Microsoft Foundation Class\).|  
|Resource.h|*Nomprojet*|Fichiers d'en\-tête|Fichier d'en\-tête des ressources qui contient les définitions des ressources utilisées par le projet.|  
|*Nomprojet*.rc2|*Nomprojet*\\res|Fichiers sources|Fichier de script qui contient les ressources supplémentaires utilisées par le projet.  Vous pouvez ajouter le fichier .rc2 en haut du fichier .rc associé au projet.<br /><br /> Un fichier .rc2 s'avère utile pour ajouter des ressources utilisées par plusieurs projets différents.  En effet, au lieu de créer les mêmes ressources pour chaque projet, vous pouvez les regrouper dans un fichier .rc2 et ajouter ce dernier au fichier .rc principal.|  
|*Nomprojet*.def|*Nomprojet*|Fichiers sources|Fichier de définition de module pour un projet de DLL.  Dans le cas d'un contrôle, ce fichier fournit le nom et la description du contrôle ainsi que la taille du tas au moment de l'exécution.|  
|*Nomprojet*.ico|*Nomprojet*\\res|Fichiers de ressources|Fichier icône pour le projet ou le contrôle.  L'icône s'affiche lorsque l'application est réduite.  Elle figure également dans la boîte de dialogue **À propos de** relative à l'application.  Par défaut, MFC fournit l'icône MFC et ATL, l'icône ATL.|  
|*Nomprojet*Doc.ico|*Nomprojet*\\res|Fichiers de ressources|Fichier icône pour un projet MFC qui offre une prise en charge de l'architecture document\/vue.|  
|Toolbar.bmp|*Nomprojet*\\res|Fichiers de ressources|Fichier bitmap représentant l'application ou le contrôle dans une barre d'outils ou une palette.  Cette bitmap est intégrée au fichier de ressources du projet.  La barre d'outils et la barre d'état initiales sont construites dans la classe **CMainFrame**.|  
|ribbon.mfcribbon\-ms|*Nomprojet*\\res|Fichiers de ressources|Fichier de ressources qui contient le code XML définissant les boutons, les contrôles et les attributs dans le ruban.  Pour plus d'informations, consultez [Concepteur de ruban \(MFC\)](../mfc/ribbon-designer-mfc.md).|  
  
## Voir aussi  
 [Types de fichiers créés pour les projets Visual C\+\+](../ide/file-types-created-for-visual-cpp-projects.md)