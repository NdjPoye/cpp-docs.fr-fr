---
title: "Utilisation de documents | Microsoft Docs"
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
  - "données (MFC), documents"
  - "données (MFC), lire"
  - "architecture Document/Vue (C++), documents"
  - "documents (C++)"
  - "documents (C++), applications C++"
  - "fichiers (C++)"
  - "fichiers (C++), écrire dans"
  - "imprimer (MFC), documents"
  - "lire des données (C++), documents et vues"
  - "vues (C++), applications C++"
  - "écrire dans les fichiers (C++)"
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de documents
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisation des documents et vues  
  
-   Contiennent, gérer, et afficher votre [données](../mfc/managing-data-with-document-data-variables.md)spécifique à l'application.  
  
-   Fournit une interface [documenter les variables de données](../mfc/managing-data-with-document-data-variables.md) composée pour manipuler les données.  
  
-   Participent à [fichiers de lecture et de lecture](../mfc/serializing-data-to-and-from-files.md).  
  
-   Participent à [imprimer](../mfc/role-of-the-view-in-printing.md).  
  
-   [Descripteur](../mfc/handling-commands-in-the-document.md) la plupart des commandes et des messages de votre application.  
  
 Le document implicite en particulier lorsque vous gérez des données.  Stockez vos données, en général, dans des variables de membre de la classe de document.  La vue utilise ces variables pour accéder aux données pour l'affichage et la mise à jour.  Le mécanisme recommandé de la sérialisation du document gère la lecture et l'écriture des données vers et à partir de fichiers.  Les documents peuvent également les commandes de traitement \(mais pas les messages windows autres que **WM\_COMMAND**\).  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Dérivation d'une classe de document de CDocument](../mfc/deriving-a-document-class-from-cdocument.md)  
  
-   [Gestion des données avec variables de données de document](../mfc/managing-data-with-document-data-variables.md)  
  
-   [Sérialisation des données dans et depuis des fichiers](../mfc/serializing-data-to-and-from-files.md)  
  
-   [Ignorer le mécanisme de sérialisation](../mfc/bypassing-the-serialization-mechanism.md)  
  
-   [Gestion des commandes dans le document](../mfc/handling-commands-in-the-document.md)  
  
-   [Reportez\-vous à la fonction membre WCode.](../Topic/CDocument::OnNewDocument.md)  
  
-   [La fonction membre du DeleteContents](../Topic/CDocument::DeleteContents.md)  
  
## Voir aussi  
 [Architecture document\/vue](../mfc/document-view-architecture.md)