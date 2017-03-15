---
title: "Pages et feuilles de propri&#233;t&#233;s (MFC) | Microsoft Docs"
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
  - "CPropertyPage (classe), pages et feuilles de propriétés"
  - "CPropertySheet (classe), pages et feuilles de propriétés"
  - "boîtes de dialogue MFC, onglets"
  - "pages de propriétés, feuilles de propriétés"
  - "feuilles de propriétés, propert (pages)"
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Pages et feuilles de propri&#233;t&#233;s (MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une MFC [boîte de dialogue](../mfc/dialog-boxes.md) peut prendre un aspect de « dialogue d'onglets » en incorporant des feuilles de propriétés et des pages de propriétés.  Appelé « feuille de propriétés » de MFC, ce type de la boîte de dialogue, semblable à de nombreuses boîtes de dialogue dans Microsoft Word, Excel, et Visual C\+\+, semble contenir une pile de pages avec onglets, comme une pile de dossiers de fichiers visibles de l'avant, ou un groupe de fenêtres empilées.  Les contrôles sur l'onglet plan sont visibles ; seul l'onglet intitulé est visible sous les onglets restaurés.  Les feuilles de propriétés sont particulièrement utiles pour gérer un grand nombre de propriétés ou des paramètres qui se situent de manière suffisamment ordonnée en plusieurs groupes.  En général, une feuille de propriétés peut simplifier une interface utilisateur en remplaçant plusieurs boîtes de dialogue distinctes.  
  
 À compter de la version 4.0 de MFC, les feuilles de propriétés et les pages de propriétés sont implémentées à l'aide des contrôles communs provenant de la version 3.51 de Windows 95 et Windows NT et des versions ultérieures.  
  
 Les feuilles de propriétés sont exécutées avec des classes [CPropertySheet](../mfc/reference/cpropertysheet-class.md) et [CPropertyPage](../mfc/reference/cpropertypage-class.md) \(décrites dans *le guide de MFC*\).  `CPropertySheet` définit la boîte de dialogue totale, qui peut contenir plusieurs « pages » basées sur `CPropertyPage`.  
  
 Pour plus d'informations sur la création et l'utilisation des feuilles de propriétés, consultez la rubrique [Feuilles de propriétés](../mfc/property-sheets-mfc.md).  
  
## Voir aussi  
 [Boîtes de dialogue](../mfc/dialog-boxes.md)   
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)   
 [Pages et feuilles de propriétés dans MFC](../mfc/property-sheets-and-property-pages-in-mfc.md)   
 [Échange des données](../mfc/exchanging-data.md)   
 [Création d'une feuille de propriétés non modale](../mfc/creating-a-modeless-property-sheet.md)   
 [Gestion du bouton Appliquer](../mfc/handling-the-apply-button.md)