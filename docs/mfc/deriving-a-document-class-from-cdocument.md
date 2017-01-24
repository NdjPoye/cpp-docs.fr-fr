---
title: "D&#233;rivation d&#39;une classe de document de CDocument | Microsoft Docs"
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
  - "CDocument (classe), dériver de"
  - "classes (C++), dériver de CDocument"
  - "classes dérivées, fonctions souvent remplacées"
  - "classes de documents, fonctions souvent remplacées"
  - "objets Document, dérivés"
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;rivation d&#39;une classe de document de CDocument
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les documents contiennent et gèrent vos données d'application.  Pour utiliser l'assistant d'application MFC\- fournie par la classe du document, vous devez effectuer les opérations suivantes :  
  
-   Dérivez une classe de **CDocument** pour chaque type de document.  
  
-   Ajoutez les variables membres pour stocker les données de chaque document.  
  
-   Ignore **CDocument** `Serialize` membre de votre classe de document.  `Serialize` écrit et lit les données du document vers le disque.  
  
## Les autres fonctions de document souvent remplacées  
 Vous pouvez également substituer d'autres fonctions membres du **CDocument**.  En particulier, vous devrez souvent remplacer [OnNewDocument](../Topic/CDocument::OnNewDocument.md) et [OnOpenDocument](../Topic/CDocument::OnOpenDocument.md) pour initialiser les données du document et [DeleteContents](../Topic/CDocument::DeleteContents.md) pour détruire les données dynamiquement allouées.  Pour plus d'informations sur les membres substituables, consultez la classe [CDocument](../mfc/reference/cdocument-class.md) dans  *guide de MFC*.  
  
## Voir aussi  
 [Utilisation de documents](../mfc/using-documents.md)