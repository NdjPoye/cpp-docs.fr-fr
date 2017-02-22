---
title: "Classes de bo&#238;tes de dialogue communes | Microsoft Docs"
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
  - "boîtes de dialogue communes (C++)"
  - "boîtes de dialogue communes (C++), classes de boîtes de dialogue communes"
  - "classes de boîtes de dialogue communes (C++)"
  - "boîtes de dialogue (C++), boîtes de dialogue Windows communes"
  - "classes de boîte de dialogue (C++)"
  - "classes de boîte de dialogue (C++), communes"
  - "boîtes de dialogue MFC, boîtes de dialogue Windows communes"
  - "boîtes de dialogue Windows communes (C++)"
ms.assetid: 5c4f6443-896c-4b05-a7df-8169fdadc71d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Classes de bo&#238;tes de dialogue communes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En plus de la classe [CDialog](../mfc/reference/cdialog-class.md), MFC fournit plusieurs classes dérivées de `CDialog` qui encapsulent les boîtes de dialogue utilisées en général, comme indiqué dans le tableau suivant.  Les boîtes de dialogue incluses sont appelées « les boîtes de dialogue communes » et font partie de la bibliothèque commune de dialogue windows \(COMMDLG.DLL\).  Les ressources modèles de la boîte de dialogue et le code de ces classes sont disponibles dans les boîtes de dialogue communes windows qui font partie des versions de Windows 3,1 et versions ultérieures.  
  
### Classes de boîtes de dialogue communes  
  
|Classe de la boîte de dialogue dérivée|Objectif|  
|--------------------------------------------|--------------|  
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|Permet à l'utilisateur de sélectionner des couleurs.|  
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|Permet à l'utilisateur de sélectionner un nom de fichier pour ouvrir ou enregistrer.|  
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|Permet à l'utilisateur de lancer une recherche ou de remplacement dans un fichier texte.|  
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|Permet à l'utilisateur de spécifier une police.|  
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|Permet à l'utilisateur de spécifier les informations d'un travail d'impression.|  
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Feuille de propriétés d'impression Windows 2000.|  
  
 Pour plus d'informations sur les classes de boîte de dialogue communes, consultez les noms de classe dans *le guide de MFC*.  MFC fournit également plusieurs classes de boîte de dialogue standard utilisées pour OLE.  Pour plus d'informations sur ces classes, consultez la classe de base, [COleDialog](../mfc/reference/coledialog-class.md), dans *le guide de MFC*.  
  
 Trois autres classes de MFC ont des caractéristiques comme un dialogue.  Pour plus d'informations sur les classes [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), et [CDaoRecordView](../mfc/reference/cdaorecordview-class.md), consultez la classe dans *le guide de MFC*.  Pour plus d'informations sur la classe [CDialogBar](../mfc/reference/cdialogbar-class.md), consultez [Barres de la boîte de dialogue](../mfc/dialog-bars.md).  
  
## Voir aussi  
 [Boîtes de dialogue](../mfc/dialog-boxes.md)   
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)   
 [Boîtes de dialogue dans OLE](../mfc/dialog-boxes-in-ole.md)