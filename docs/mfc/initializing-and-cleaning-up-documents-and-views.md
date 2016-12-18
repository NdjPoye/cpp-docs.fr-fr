---
title: "Initialisation et nettoyage des documents et vues | Microsoft Docs"
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
  - "objets Document, cycle de vie de"
  - "documents, nettoyage"
  - "documents, initialiser"
  - "initialiser des documents"
  - "initialiser des objets, objets Document"
  - "Initialiser des vues"
  - "vues, nettoyage"
  - "vues, initialiser"
ms.assetid: 95d6f09b-a047-4079-856a-ae7d0548e9d2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Initialisation et nettoyage des documents et vues
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez les instructions suivantes pour initialiser et nettoyer après vos documents et vues :  
  
-   L'infrastructure MFC initialise des documents et des vues ; vous initialisez toutes les données que vous ajoutez à celles\-ci.  
  
-   L'infrastructure nettoie les documents et les vues se ferment ; vous devez récupérer toute mémoire que vous avez allouée sur le segment depuis les fonctions membres de ces documents et des vues.  
  
> [!NOTE]
>  N'oubliez pas que l'initialisation de l'application entière est au mieux créée à votre substitution de la fonction membre de [InitialiserInstance](../Topic/CWinApp::InitInstance.md) de la classe `CWinApp`, et le nettoyage de l'application du mieux s'effectue dans la substitution de la fonction membre [QuitterInstance](../Topic/CWinApp::ExitInstance.md)de `CWinApp`.  
  
 Le cycle de vie d'un document \(et sa fenêtre cadre et vue ou vues\) dans une application MDI est la suivante :  
  
1.  Lors de la création dynamique, le constructeur de document est appelé.  
  
2.  Pour chaque document, [SurNouveauDocument](../Topic/CDocument::OnNewDocument.md) ou [SurDocumentOuvert](../Topic/CDocument::OnOpenDocument.md) du document est appelé.  
  
3.  L'utilisateur interagit avec le document durant toute la durée de vie.  Généralement cela se produit pendant que l'utilisateur utilise des données de document par le biais de la vue, la sélection et la modification des données.  La vue transmet les modifications apportées au document pour le stockage et la mise à jour d'autres vues.  Pendant ce temps le document et la vue peuvent gérer des commandes.  
  
4.  L'infrastructure appelle [DeleteContents](../Topic/CDocument::DeleteContents.md) pour supprimer les données propres à un document.  
  
5.  Le destructeur du document est appelé.  
  
 Dans une application de SDI, l'étape 1 est effectuée une seule fois, lorsque le document est d'abord créé.  Les étapes 2 et 4 sont effectuées à plusieurs reprises chaque fois qu'un document est ouvert.  Le document réutilise l'objet document existant.  Enfin, l'étape 5 est effectuée lorsque l'application se termine.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Initialisation des documents et vues](../mfc/initializing-documents-and-views.md)  
  
-   [Nettoyage des documents et vues](../mfc/cleaning-up-documents-and-views.md)  
  
## Voir aussi  
 [Architecture document\/vue](../mfc/document-view-architecture.md)