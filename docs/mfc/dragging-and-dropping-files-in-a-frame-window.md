---
title: "Glisser-d&#233;placer des fichiers dans une fen&#234;tre frame | Microsoft Docs"
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
  - "glisser-déplacer (C++), Gestionnaire de fichiers"
  - "glisser-déplacer (C++), fichiers"
  - "glisser-déplacer (C++), Explorateur Windows"
  - "Gestionnaire de fichiers (glisser-déplacer) (prise en charge)"
  - "fichiers (C++), glisser-déplacer"
  - "fenêtres frame (C++), glisser-déplacer des fichiers dans"
  - "Explorateur Windows (C++)"
ms.assetid: 85560fe9-121b-4105-bd7b-216b966e19fa
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Glisser-d&#233;placer des fichiers dans une fen&#234;tre frame
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La fenêtre cadre gère la relation avec l'Explorateur de fichiers ou le gestionnaire de fichiers.  
  
 En ajoutant quelques appels d'initialisation lors de la réécriture de la fonction `InitInstance` de `CWinApp`, comme décrit dans [CWinApp : La classe d'application](../mfc/cwinapp-the-application-class.md), vous pouvez faire ouvrir de manière indirecte par votre fenêtre les fichiers glissés depuis l'Explorateur de fichiers ou le Gestionnaire de fichiers et déposés dans cette fenêtre.  Voir le [Gestionnaire de fichiers \(Glisser\-Déposer\)](../mfc/special-cwinapp-services.md).  
  
## Voir aussi  
 [Utilisation de fenêtres frame](../mfc/using-frame-windows.md)