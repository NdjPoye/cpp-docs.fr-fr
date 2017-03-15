---
title: "Mod&#232;les de document et processus de cr&#233;ation de document/vue | Microsoft Docs"
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
  - "CDocTemplate (classe)"
  - "modèles de document, et vues"
  - "architecture document/vue, créer un document/une vue"
  - "icônes, pour modèles multidocuments"
  - "MFC, modèles de document"
  - "modèle multidocument"
  - "modèle mono document"
  - "modèles, modèles de document"
ms.assetid: 311ce4cd-fbdf-4ea1-a51b-5bb043abbcee
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mod&#232;les de document et processus de cr&#233;ation de document/vue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour gérer le processus complexe de création de documents avec les vues associées et cadres de fenêtres, l'infrastructure utilise deux classes du modèle de document : [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) pour les demandes de SDI et [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) d'applications MDI.  Un `CSingleDocTemplate` peut créer et stocker un document d'un type à la fois.  Un `CMultiDocTemplate` conserve une liste de plusieurs documents ouverts d'un type.  
  
 Certaines applications prennent en charge plusieurs types de documents.  Par exemple, une application peut prendre en charge les documents texte et les documents graphiques.  Dans une telle application, lorsque l'utilisateur sélectionne la commande Nouveau du menu Fichier, une boîte de dialogue affiche une liste des nouveaux types de documents possibles à ouvrir.  Pour chaque type de document pris en charge, l'application utilise un objet distinct modèle de document.  La figure suivante illustre la configuration d'une application MDI que prend en charge deux types de documents et montre plusieurs documents ouverts.  
  
 ![Application MDI qui possède deux types de document](../mfc/media/vc387h1.png "vc387H1")  
Une Application MDI qui possède deux types de documents  
  
 Les modèles de document sont créés et entretenus par l'objet d'application.  L'une des tâches clé effectuées pendant la fonction d' `InitInstance` de votre application consiste à créer un ou plusieurs modèles de document du type approprié.  Cette fonctionnalité est décrite dans [Création d'un modèle de document](../mfc/document-template-creation.md).  L'objet d'application enregistre un pointeur à chaque modèle de document dans sa liste de modèles et fournit une interface pour ajouter des modèles de document.  
  
 Si vous devez assurer la prise en charge de deux types de documents ou plus, vous devez ajouter un appel supplémentaire à [AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md) pour chaque type de document.  
  
 Une icône est stockée pour chaque modèle de document en fonction de sa position dans la liste des applications de modèles de document.  L'ordre des modèles de document est déterminé par l'ordre dans lequel ils sont ajoutés avec les appels de `AddDocTemplate`.  MFC suppose que la première ressource d'icône dans l'application est l'icône d'application, la ressource d'icône suivante est la première icône de document, et ainsi de suite.  
  
 Par exemple, un modèle de document est la troisième icône sur trois pour l'application.  S'il existe une ressource d'icône dans l'application à l'index 3, cette icône est utilisée pour le modèle de document.  Sinon, l'icône à l'index 0 est utilisée comme valeur par défaut.  
  
## Voir aussi  
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)   
 [Création de modèle de document](../mfc/document-template-creation.md)   
 [Création d'un document\/d'une vue](../mfc/document-view-creation.md)   
 [Relations entre les objets MFC](../mfc/relationships-among-mfc-objects.md)   
 [Création de documents, fenêtres et vues](../mfc/creating-new-documents-windows-and-views.md)