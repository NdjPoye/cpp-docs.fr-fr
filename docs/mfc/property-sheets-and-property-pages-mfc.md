---
title: "Feuilles de propriétés et Pages de propriétés (MFC) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], tabs
- property pages [MFC], property sheets
- CPropertyPage class [MFC], property sheets and pages
- CPropertySheet class [MFC], property sheets and pages
- property sheets, propert pages
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 877d83a6833b9505c326bc5312d2f151add07cb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="property-sheets-and-property-pages-mfc"></a>Pages et feuilles de propriétés (MFC)
Une MFC [boîte de dialogue](../mfc/dialog-boxes.md) peuvent effectuer sur un aspect « onglet de boîte de dialogue » en incorporant des feuilles de propriétés et pages de propriétés. Ce type de boîte de dialogue similaire à nombreuses boîtes de dialogue dans Microsoft Word, Excel et Visual C++, appelé « feuille de propriétés » dans MFC, apparaît pour contenir une pile de feuilles à onglets, comme une pile de dossiers de fichiers vu avant vers l’arrière, ou un groupe de fenêtres en cascade. Contrôles sous l’onglet serveur frontal sont visibles ; seul l’onglet étiqueté est visible dans les onglets. Feuilles de propriétés sont particulièrement utiles pour la gestion de grands nombres de propriétés ou paramètres qui se situent assez nettement en plusieurs groupes. En règle générale, une feuille de propriétés peut simplifier une interface utilisateur en remplaçant plusieurs boîtes de dialogue distincte.  
  
 Depuis la version 4.0 de MFC, les feuilles de propriétés et pages de propriétés sont implémentées à l’aide de contrôles communs livrés avec la version de Windows 95 et Windows NT 3.51 et ultérieure.  
  
 Feuilles de propriétés sont implémentées avec les classes [CPropertySheet](../mfc/reference/cpropertysheet-class.md) et [CPropertyPage](../mfc/reference/cpropertypage-class.md) (décrit dans la *référence MFC*). `CPropertySheet`définit la boîte de dialogue globale, qui peut contenir plusieurs « pages » selon `CPropertyPage`.  
  
 Pour plus d’informations sur la création et l’utilisation des feuilles de propriétés, consultez la rubrique [feuilles de propriétés](../mfc/property-sheets-mfc.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Boîtes de dialogue](../mfc/dialog-boxes.md)   
 [Cycle de vie d’une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)   
 [Feuilles de propriétés et Pages de propriétés dans MFC](../mfc/property-sheets-and-property-pages-in-mfc.md)   
 [Échange de données](../mfc/exchanging-data.md)   
 [Création d’une feuille de propriétés non modale](../mfc/creating-a-modeless-property-sheet.md)   
 [Gestion du bouton Appliquer](../mfc/handling-the-apply-button.md)

