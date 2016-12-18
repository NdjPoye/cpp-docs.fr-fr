---
title: "Architecture document/vue | Microsoft Docs"
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
  - "CDocument (classe)"
  - "CView (classe), architecture vue"
  - "objets Document"
  - "objets Document, architecture document/vue"
  - "objets Document, modèle de vue/document MFC"
  - "documents, modèle de vue/document MFC"
  - "MFC, documents"
  - "MFC, vues"
  - "vues, modèle de vue/document MFC"
ms.assetid: 6127768a-553f-462a-b01b-a5ee6068c81e
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Architecture document/vue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Par défaut, l'Application MFC crée une structure d'application à une classe de document et une classe d'affichage.  MFC sépare la gestion de données dans deux classes.  Le document stocke les données et gère les impressions les données et les coordonnées mettre à jour plusieurs vues de données.  La vue affiche les données et gère l'interaction de l'utilisateur avec cette connexion, notamment la sélection et la modification.  
  
 Dans ce modèle, un objet document de MFC lit et écrit des données dans la mémoire permanente.  Le document peut également fournir une interface aux données où il réside \(comme dans une base de données\).  Un objet de vue distincte gère l'affichage de données, de la consultation des données dans une fenêtre à la sélection par l'utilisateur et la modification des données.  Obtient la vue afficher les données du document et transmet au document toutes les modifications de données.  
  
 Vous pouvez facilement remplacer ou ignorer la séparation de documents\/vue, il existe des raisons indiscutables pour suivre ce modèle dans la plupart des cas.  L'un des meilleurs est lorsque vous avez besoin de plusieurs vues du même document, telles qu'une feuille de calcul et une vue Graphique.  Le document\/modèle de vue d'un objet de vue distinct représenter chaque vue des données, tandis que le code commun à toutes vues \(tel qu'un moteur de calcul\) peut résider dans le document.  Le document prend également la tâche de mise à jour toutes les vues chaque fois que les modifications de données.  
  
 L'architecture documents\/Vue de MFC est ainsi facile de prendre en charge plusieurs vues, types de document, fractionnement de fenêtres, et d'autres fonctionnalités de l'interface utilisateur précieuses.  
  
 Les parties de l'infrastructure MFC la plus visible par l'utilisateur et vous, le programmeur, sont le document et la vue.  La plupart de votre travail en développement d'application avec l'infrastructure va consister en l'écriture de votre document et des classes d'affichage.  La famille d'article explique :  
  
-   Les opérations des documents et des vues et comment elles interagissent dans l'infrastructure.  
  
-   Ce que vous devez faire à implémenter.  
  
 Au cœur du document ou de la vue sont quatre classes principales :  
  
 La classe [CDocument](../mfc/reference/cdocument-class.md) \(ou [COleDocument](../mfc/reference/coledocument-class.md)\) prend en charge les objets utilisés pour signaler ou contrôler les données de votre programme et fournit des fonctionnalités de base pour les classes programmeur\- définies de document.  Un document représente l'unité de données de l'utilisateur en général ouvre avec la commande ouverte dans le menu Fichier et enregistre à la commande de sauvegarde dans le menu Fichier.  
  
 [CView](../mfc/reference/cview-class.md) \(ou une de ses nombreuses classes dérivées\) fournit des fonctionnalités de base pour les classes d'affichage programmeur\- définies.  Une vue est attachée à un document et agit comme intermédiaire entre le document et l'utilisateur : la vue affiche une image du document à l'écran et interprète une entrée utilisateur comme opérations sur le document.  La vue affiche également l'image pour l'impression et l'aperçu avant impression.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md) \(ou une de ses variantes\) prend en charge les objets fournis par le cadre autour d'une ou plusieurs vues d'un document.  
  
 [CDocTemplate](../mfc/reference/cdoctemplate-class.md) \(ou [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) ou [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)\) prend en charge un objet qui coordonne un ou de plusieurs documents existants d'un type donné et gère la création de document correct, la vue, et les objets appropriés de fenêtre cadre de ce type.  
  
 L'illustration suivante montre la relation entre un document et son affichage.  
  
 ![La vue est la partie du document qui s'affiche](../mfc/media/vc379n1.png "vc379N1")  
Document et vue  
  
 L'implémentation de documents\/vue dans la bibliothèque de classes sépare les données proprement dites de leur affichage et les opérations d'utilisateur sur les données.  Toutes les modifications des données sont gérées via la classe de document.  Elle appelle cette interface permet d'accéder et de mettre à jour des données.  
  
 Les documents, les vues associées, et les fenêtres cadres qui encadrent les vues sont créées par un modèle de document.  Le modèle de document est chargé de créer et de gérer tous les documents d'un type de document.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Un portrait de l'architecture document\/vue](../mfc/a-portrait-of-the-document-view-architecture.md)  
  
-   [Avantages de l'architecture document\/vue](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [Document et classes d'affichages créés par l'Assistant Application MFC](../mfc/document-and-view-classes-created-by-the-mfc-application-wizard.md)  
  
-   [Solutions de remplacement de l'architecture document\/vue](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [Ajout de plusieurs vues à un seul document](../mfc/adding-multiple-views-to-a-single-document.md)  
  
-   [Utilisation de documents](../mfc/using-documents.md)  
  
-   [Utilisation de vues](../mfc/using-views.md)  
  
-   [Types multidocuments, vues et fenêtres frame](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [Initialisation et nettoyage des documents et affichages](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
-   [Initialiser vos propres ajouts pour documenter & les classes d'affichage](../mfc/creating-new-documents-windows-and-views.md)  
  
-   [Utilisation des classes de bases de données avec des documents et des vues](../data/mfc-using-database-classes-with-documents-and-views.md)  
  
-   [Utilisation des classes de bases de données sans document ni vue](../data/mfc-using-database-classes-without-documents-and-views.md)  
  
-   [Exemples](../top/visual-cpp-samples.md)  
  
## Voir aussi  
 [Éléments de l'interface utilisateur](../mfc/user-interface-elements-mfc.md)   
 [Windows](../mfc/windows.md)   
 [Fenêtres frame](../mfc/frame-windows.md)   
 [Modèles de document et processus de création de document\/vue](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Création d'un document\/d'une vue](../mfc/document-view-creation.md)   
 [Création de documents, fenêtres et vues](../mfc/creating-new-documents-windows-and-views.md)