---
title: "Fichiers d&#39;aide (aide HTML) | Microsoft Docs"
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
  - "types de fichiers (C++), fichiers d'aide HTML"
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fichiers d&#39;aide (aide HTML)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fichiers suivants sont créés lorsque vous ajoutez à votre application une prise en charge de l'aide de type HTML, ceci en activant la case à cocher **Aide contextuelle** puis en sélectionnant **HTML** dans la page [Fonctionnalités avancées](../mfc/reference/advanced-features-mfc-application-wizard.md) de l'Assistant Application MFC.  
  
|Nom du fichier|Emplacement dans les répertoires|Emplacement dans l'Explorateur de solutions|Description|  
|--------------------|--------------------------------------|-------------------------------------------------|-----------------|  
|*Nomprojet*.hhp|*Nomprojet*\\hlp|Fichiers d'aide HTML|Fichier projet d'aide.  Il contient les données nécessaires à la compilation des fichiers d'aide en un fichier .hxs ou .chm.|  
|*Nomprojet*.hhk|*Nomprojet*\\hlp|Fichiers d'aide HTML|Contient un index des rubriques d'aide.|  
|*Nomprojet*.hhc|*Nomprojet*\\hlp|Fichiers d'aide HTML|Contenu du projet d'aide.|  
|Makehtmlhelp.bat|*Nomprojet*|Fichiers sources|Fichier utilisé par le système pour générer le projet d'aide lors de la compilation du projet.|  
|Afxcore.htm|*Nomprojet*\\hlp|Rubriques d'aide HTML|Contient les rubriques d'aide standard relatives aux objets de l'écran et commandes MFC.  Ajoutez à ce fichier vos propres rubriques d'aide.|  
|Afxprint.htm|*Nomprojet*\\hlp|Rubriques d'aide HTML|Contient les rubriques d'aide relatives aux commandes d'impression.|  
|\*.jpg ; \*.gif|*Nomprojet*\\hlp\\Images|Fichiers de ressources|Contient les images affichées dans les différentes rubriques d'aide générées.|  
  
## Voir aussi  
 [Types de fichiers créés pour les projets Visual C\+\+](../ide/file-types-created-for-visual-cpp-projects.md)