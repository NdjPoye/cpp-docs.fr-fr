---
title: "Nettoyage des documents et vues | Microsoft Docs"
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
  - "documents, nettoyage"
  - "documents, fermer"
  - "vues, nettoyage"
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Nettoyage des documents et vues
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'un document se ferme, le framework appelle d'abord la fonction membre de [DeleteContents](../Topic/CDocument::DeleteContents.md).  Si vous allouez de la mémoire sur le segment de mémoire au cours des opérations du document, `DeleteContents` est le meilleur endroit pour la libérer.  
  
> [!NOTE]
>  Vous ne devez pas récupérer les données du document dans le destructeur du document.  Dans le cas d'une application SDI, l'objet document peut être réutilisé.  
  
 Vous pouvez remplacer le destructeur d'une vue pour récupérer toute mémoire que vous avez allouée sur le segment.  
  
## Voir aussi  
 [Initialisation et nettoyage des documents et vues](../mfc/initializing-and-cleaning-up-documents-and-views.md)