---
title: "Personnalisation pour MFC | Microsoft Docs"
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
  - "personnalisations, extensions MFC"
ms.assetid: 3b1b7532-8cc9-48dc-9bbe-7fd4060530b5
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Personnalisation pour MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique fournit des conseils pour personnaliser une application de MFC.  
  
## Personnalisations générales  
 Vous pouvez enregistrer et charger l'état de votre application dans le Registre.  Lorsque vous activez cette option, l'application charge son état initial du Registre.  Si vous modifiez la mise en page initiale d'ancrage pour votre application, vous devez désactiver les données de Registre de votre application.  Sinon, les données du Registre remplaceront toutes les modifications apportées à la mise en page initiale.  
  
## Personnalisations de classe spécifique  
 Les conseils supplémentaires de personnalisation se trouvent dans les rubriques suivantes :  
  
-   [CBasePane Class](../mfc/reference/cbasepane-class.md)  
  
-   [CDockablePane Class](../mfc/reference/cdockablepane-class.md)  
  
-   [CDockingManager Class](../mfc/reference/cdockingmanager-class.md)  
  
-   [CMFCBaseTabCtrl Class](../mfc/reference/cmfcbasetabctrl-class.md)  
  
## Conseils supplémentaires de personnalisation  
 [Personnalisation du clavier et de la souris](../mfc/keyboard-and-mouse-customization.md)  
  
 [Outils définis par l'utilisateur](../mfc/user-defined-tools.md)  
  
## Voir aussi  
 [MFC, applications de bureau](../mfc/mfc-desktop-applications.md)   
 [Implications en matière de sécurité de la personnalisation](../mfc/security-implications-of-customization.md)