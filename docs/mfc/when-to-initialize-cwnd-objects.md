---
title: "Quand initialiser les objets CWnd | Microsoft Docs"
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
  - "objets CWnd, lorsque HWND est attaché"
  - "objets CWnd, quand initialiser"
  - "HWND, lorsqu'il est attaché à un objet CWnd"
  - "initialiser des objets CWnd"
  - "initialiser des objets, CWnd"
  - "objets fenêtres, quand initialiser CWnd"
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Quand initialiser les objets CWnd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous ne pouvez pas créer vos propres fenêtres enfants ou appeler les fonctions API Windows dans le constructeur d'un objet dérivé de `CWnd`.  Cela est dû au fait que `HWND` de l'objet `CWnd` n'a pas encore été créé.  La plupart de l'initialisation spécifique à Windows, telles l'ajout de fenêtres enfants, doit être effectuée dans un gestionnaire de messages [OnCreate](../Topic/CWnd::OnCreate.md).  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Création de fenêtres de cadre de document](../mfc/creating-document-frame-windows.md)  
  
-   [Création document\/vue](../mfc/document-view-creation.md)  
  
## Voir aussi  
 [Utilisation de fenêtres frame](../mfc/using-frame-windows.md)