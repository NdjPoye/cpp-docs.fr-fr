---
title: "Cr&#233;ation d&#39;un document/d&#39;une vue | Microsoft Docs"
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
  - "architecture document/vue, créer un document/une vue"
  - "documents, créer"
  - "MFC, documents"
  - "MFC, vues"
  - "créateurs d'objets"
  - "tables (C++)"
  - "tables (C++), objets que chaque objet MFC crée"
  - "vues, et fenêtres frame"
  - "vues, créer"
ms.assetid: bda14f41-ed50-439d-af9e-591174e7dd64
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Cr&#233;ation d&#39;un document/d&#39;une vue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'infrastructure fournit des implémentations des commandes `New` et **Ouvrir** \(entre autres choses\) dans le menu **Fichier**.  La création d'un nouveau document et sa vue et sa fenêtre de cadre associée est un effort de coopération entre l'objet d'application, un modèle de document, le document nouvellement créé, et la fenêtre cadre nouvellement créé.  Le tableau suivant récapitule quels objets créent quoi  
  
### créateurs d'objets  
  
|Création|Crée|  
|--------------|----------|  
|Objet application|modèle de document|  
|modèle de document|Document|  
|modèle de document|fenêtre de cadre|  
|fenêtre de cadre|Vue|  
  
## Voir aussi  
 [Modèles de document et processus de création de document\/vue](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Création de modèle de document](../mfc/document-template-creation.md)   
 [Relations entre les objets MFC](../mfc/relationships-among-mfc-objects.md)   
 [Création de documents, fenêtres et vues](../mfc/creating-new-documents-windows-and-views.md)