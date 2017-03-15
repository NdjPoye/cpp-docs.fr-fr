---
title: "Destruction du contr&#244;le de liste | Microsoft Docs"
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
  - "CListCtrl (classe), détruire des contrôles"
  - "contrôles de liste, détruire"
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Destruction du contr&#244;le de liste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous incluez l'objet [CListCtrl](../mfc/reference/clistctrl-class.md) en tant que membre de données d'une vue ou d'une classe de dialogue, il est détruit lorsque son propriétaire est détruit.  Si vous utilisez [CListView](../mfc/reference/clistview-class.md), l'infrastructure détruit le contrôle lorsqu'elle détruit la vue.  
  
 Si vous faites en sorte que certaines de vos données de liste soient stockées dans l'application et non par le contrôle de liste, vous devez fournir la désallocation.  Pour plus d'informations, consultez [Éléments de rappel et masque de rappel](http://msdn.microsoft.com/library/windows/desktop/bb774736) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 En outre, vous êtes chargé de libérer toutes les listes d'images que vous avez créées et associées à l'objet de contrôle de liste.  
  
## Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)