---
title: "Int&#233;gration du format OLE au format MFC | Microsoft Docs"
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
  - "applications (OLE), à propos de OLE"
  - "MFC (C++), OLE et"
  - "OLE (C++)"
  - "OLE (applications) (C++), à propos de OLE"
  - "modèle objet composant OLE (COM)"
  - "conteneurs OLE, à propos de OLE"
  - "OLE (éléments)"
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Int&#233;gration du format OLE au format MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces articles expliquent les aspects fondamentaux de la programmation OLE à l'aide de MFC.  MFC offre la méthode la plus simple pour écrire des programmes qui utilisent OLE :  
  
-   Pour utiliser la modification visuelle OLE \(activation en place\).  
  
-   Pour utiliser comme conteneurs ou serveurs OLE.  
  
-   Pour implémenter des fonctionnalités de glisser\-déplacer.  
  
-   Pour utiliser des données de date et d'heure.  
  
-   Pour gérer les données d'état des modules MFC, y compris les points d'entrée exportés des points d'entrée de la fonction DLL, de l'interface OLE\/COM, et de procédure d'affichage.  
  
 Vous pouvez également utiliser [Automation](../mfc/automation.md) ou [Remote Automation](../mfc/remote-automation.md) pour commander un autre programme de votre programme.  
  
> [!NOTE]
>  Le terme OLE indique les technologies associées à la liaison et l'incorporation, y compris les conteneurs OLE, les serveurs OLE, les éléments OLE, l'activation en place \(ou la modification visuelle\), les trackers, le glisser\/déplacer, et la fusion de menus.  Le terme Active s'applique au modèle d'objet composant \(COM\) et aux objets basés sur COM tels que les contrôles ActiveX.  OLE Automation est maintenant appelé Automation.  
  
## Dans cette section  
 [Arrière\-plan OLE](../mfc/ole-background.md)  
 OLE décrit et fournit des informations conceptuelles à propos de son fonctionnement.  
  
 [Activation](../mfc/activation-cpp.md)  
 Décrit le rôle de l'activation de la modification de OLE éléments.  
  
 [Conteneurs](../mfc/containers.md)  
 Fournit des liens vers des conteneurs dans OLE.  
  
 [Objets de données et sources de données](../mfc/data-objects-and-data-sources-ole.md)  
 Fournit des liens vers des rubriques discutant l'utilisation des classes `COleDataObject` et `COleDataSource`.  
  
 [Glisser\-déplacer](../mfc/drag-and-drop-ole.md)  
 Explique comment utiliser le copier\/coller par OLE.  
  
 [Menus et ressources OLE](../mfc/menus-and-resources-ole.md)  
 Explique l'utilisation des menus et des ressources dans des applications de document OLE MFC.  
  
 [Inscription](../mfc/registration.md)  
 Traite de l'installation et l'initialisation du serveur.  
  
 [Serveurs](../mfc/servers.md)  
 Décrit comment créer des éléments OLE \(ou composants\) pour une utilisation par les applications conteneur.  
  
 [Trackers](../mfc/trackers.md)  
 Fournit des informations sur la classe `CRectTracker`, qui fournit une interface graphique pour permettre aux utilisateurs d'interagir avec des éléments client OLE.  
  
## Rubriques connexes  
 [Points de connexion](../mfc/connection-points.md)  
 Explique comment implémenter des points de connexion \(anciennement appelé points de connexion OLE\) à l'aide des classes `CCmdTarget` et `CConnectionPoint`de MFC.  
  
 [Composants COM de conteneur\/serveur](../mfc/containers-advanced-features.md)  
 Décrit les étapes nécessaires pour intégrer des fonctionnalités avancées optionnelles dans des applications de conteneur existantes.  
  
 [Le Component Object Model \(COM\)](http://msdn.microsoft.com/library/windows/desktop/ms694363)  
 Décrit l'utilisation de OLE sans MFC.  
  
## Voir aussi  
 [Concepts](../mfc/mfc-concepts.md)