---
title: "Ajout d&#39;&#233;l&#233;ments au contr&#244;le Header | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CHeaderCtrl (classe), ajouter des éléments"
  - "contrôles (MFC), header"
  - "contrôles header, ajouter des éléments à"
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout d&#39;&#233;l&#233;ments au contr&#244;le Header
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Après avoir créé votre contrôle d'en tête \([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)\) dans la fenêtre parente, ajoutez autant d'« éléments d'en\-tête » que nécessaire: généralement un par colonne.  
  
### Pour ajouter un élément d'en tête  
  
1.  Préparez une structure d' [HD\_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247).  
  
2.  Appelez [CHeaderCtrl::InsertItem](../Topic/CHeaderCtrl::InsertItem.md), en passant la structure.  
  
3.  Répétez les étapes 1 et 2 pour les éléments supplémentaires.  
  
 Pour plus d'informations, consultez [Ajouter un élément à un contrôle d'en tête](http://msdn.microsoft.com/library/windows/desktop/bb775238) dans le [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Voir aussi  
 [Utilisation de CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)