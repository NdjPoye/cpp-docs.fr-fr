---
title: "Menus et ressources (OLE) | Microsoft Docs"
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
  - "applications (OLE), menus et ressources"
  - "conteneurs (C++), applications conteneur OLE"
  - "activation sur place, OLE (menus et ressources)"
  - "menus (C++), documents OLE (applications)"
  - "OLE (applications) (C++), menus et ressources"
  - "conteneurs OLE, menus et ressources"
  - "OLE (menus et ressources)"
  - "applications serveur OLE, menus et ressources"
  - "OLE (serveurs d'édition visuelle)"
  - "applications serveur, OLE (menus et ressources)"
  - "barres d'état, documents OLE (applications)"
  - "modification de chaînes, applications d'édition visuelle"
  - "tables de chaînes, applications d'édition visuelle"
  - "barres d'outils (C++), documents OLE (applications)"
  - "édition visuelle, menus et ressources d'applications"
ms.assetid: 52bfa086-7d3d-466f-94c7-c7061f3bdb3a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Menus et ressources (OLE)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce groupe d'articles explique l'utilisation des menus et des ressources dans les applications de documents OLE MFC.  
  
 Exigences supplémentaires des emplacements de modifications OLE sur le menu et d'autres ressources fournies par les applications de document OLE car il existe plusieurs modes dans lesquels les applications de conteneur et de serveur \(composant\) peuvent être démarrées et utilisées.  Par exemple, une application de serveur complète peut s'exécuter dans l'un des trois modes :  
  
-   Autonome.  
  
-   En place, pour modifier un élément dans le contexte d'un conteneur.  
  
-   Ouvert, pour modifier un élément hors du contexte de son conteneur, souvent dans une fenêtre distincte.  
  
 Cela implique trois dispositions distinctes de menu, une pour chaque mode possible de l'application.  Les tables des accélérateurs sont également requises pour chaque nouveau mode.  Une application conteneur peut prendre ou ne pas prendre en charge l'activation sur place ; si c'est le cas, elle exige en effet une structure de menu et les tables des accélérateurs associées.  
  
 L'activation sur place nécessite que le conteneur et les applications serveur doivent négocier pour le menu, la barre d'outils, et l'espace de barre d'état.  Toutes les ressources doivent être conçues à cet effet.  L'article [Menus et de ressources : Fusion de menus](../mfc/menus-and-resources-menu-merging.md) traite de cette rubrique en détail.  
  
 En raison de ces problèmes, les applications OLE de document créées avec l'Application wizard peuvent avoir jusqu'à quatre ressources distinctes de menus et de table des accélérateurs.  Celles\-ci sont utilisées pour les raisons suivantes :  
  
|Nom des ressources|Utilisez|  
|------------------------|--------------|  
|**IDR\_MAINFRAME**|Utilisé dans une application MDI si aucun fichier n'est ouvert, ou dans une application de SDI que des fichiers soient ouverts ou non.  Il s'agit du menu standard utilisé dans les applications non OLE.|  
|**IDR\_\<Projet\>TYPE**|Utilisé dans une application MDI si les fichiers sont ouverts.  Utilisé lorsqu'une application s'exécute de manière autonome.  Il s'agit du menu standard utilisé dans les applications non OLE.|  
|**IDR\_\<project\>TYPE\_SRVR\_IP**|Utilisé par le serveur ou le conteneur lorsqu'un objet est ouvert dans l'emplacement.|  
|**IDR\_\<project\>TYPE\_SRVR\_EMB**|Utilisé par une application serveur si un objet est ouvert sans utiliser l'activation dans l'emplacement.|  
  
 Chacun de ces noms de ressource représente un menu et, en général, une table des accélérateurs.  Un modèle semblable doit être utilisée dans des applications MFC qui ne sont pas créées avec l'Application wizard.  
  
 Les éléments suivants présentent les rubriques relatives aux conteneurs, serveurs, et à la fusion de menus nécessaire pour implémenter l'activation dans l'emplacement :  
  
-   [Menus et ressources : Ajouts de conteneurs](../mfc/menus-and-resources-container-additions.md)  
  
-   [Menus et ressources : ajouts de serveurs](../mfc/menus-and-resources-server-additions.md)  
  
-   [Menus et ressource : Fusion de menus](../mfc/menus-and-resources-menu-merging.md)  
  
## Voir aussi  
 [OLE](../mfc/ole-in-mfc.md)