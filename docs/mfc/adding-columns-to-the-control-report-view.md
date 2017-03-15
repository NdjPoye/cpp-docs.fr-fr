---
title: "Ajout de colonnes au contr&#244;le (vue Rapport) | Microsoft Docs"
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
  - "CListCtrl (classe), ajouter des colonnes"
  - "CListCtrl (classe), vue Rapport"
  - "colonnes (C++), ajouter à CListCtrl"
  - "vue Rapport dans la classe CListCtrl"
  - "vues, rapport"
ms.assetid: 7392c0d7-f8a5-4e7b-9ae7-b53dc9dd80ae
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Ajout de colonnes au contr&#244;le (vue Rapport)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  The following procedure applies to either a [CListView](../mfc/reference/clistview-class.md) or [CListCtrl](../mfc/reference/clistctrl-class.md) object.  
  
 When a list control is in report view, columns are displayed, providing a method of organizing the various subitems of each list control item.  This organization is implemented with a one\-to\-one correspondence between a column in the list control and the associated subitem of the list control item.  For more information on subitems, see [Adding Items to the Control](../mfc/adding-items-to-the-control.md).  An example of a list control in report view is provided by the Details view in Windows 95 and Windows 98 Explorer.  The first column lists folder, file icons, and labels.  Other columns list file size, file type, date last modified, and so on.  
  
 Even though columns can be added to a list control at any time, the columns are visible only when the control has the `LVS_REPORT` style bit turned on.  
  
 Each column has an associated header item \(see [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)\) object that labels the column and allows users to resize the column.  
  
 If your list control supports a report view, you need to add a column for each possible subitem in a list control item.  Add a column by preparing an [LV\_COLUMN](http://msdn.microsoft.com/library/windows/desktop/bb774743) structure and then making a call to [InsertColumn](../Topic/CListCtrl::InsertColumn.md).  After adding the necessary columns \(sometimes referred to as header items\), you can reorder them using member functions and styles belonging to the embedded header control.  For more information, see [Ordering Items in the Header Control](../mfc/ordering-items-in-the-header-control.md).  
  
> [!NOTE]
>  If the list control is created with the **LVS\_NOCOLUMNHEADER** style, any attempt to insert columns will be ignored.  
  
## Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)