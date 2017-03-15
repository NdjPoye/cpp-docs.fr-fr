---
title: "Contr&#244;les de bo&#238;tes de dialogue et types de variables | Microsoft Docs"
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
  - "contrôles de boîte de dialogue, variables membres"
  - "contrôles de boîte de dialogue, types de variable"
  - "variables, variables membres de contrôle de boîte de dialogue"
ms.assetid: f9cd9cea-45a6-4349-8358-e5efbcdcff76
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Contr&#244;les de bo&#238;tes de dialogue et types de variables
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser l'[Assistant Ajout de variable membre](../ide/add-member-variable-wizard.md) pour ajouter une variable membre à un contrôle de boîte de dialogue créé à l'aide de MFC.  Le type de contrôle pour lequel vous ajoutez la variable membre détermine les options disponibles dans la boîte de dialogue.  
  
 Le tableau suivant décrit tous les types de contrôles de boîtes de dialogue pris en charge dans MFC et dans l'[Éditeur de boîtes de dialogue](../mfc/dialog-editor.md), ainsi que les types et valeurs disponibles.  
  
|Contrôle|Type de contrôle|Type de variable de contrôle|Type de variable de valeur|Valeurs min\/max \(type valeur uniquement\)|  
|--------------|----------------------|----------------------------------|--------------------------------|-------------------------------------------------|  
|Contrôle Animation|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|Aucun ; contrôle uniquement|N\/A|  
|Button|BUTTON|[CButton](../mfc/reference/cbutton-class.md)|Aucun ; contrôle uniquement|N\/A|  
|Check Box|CHECK|[CButton](../mfc/reference/cbutton-class.md)|**BOOL**|Valeur min value\/Valeur max|  
|Combo Box|COMBOBOX|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|Caractères maxi|  
|Contrôle Date Time Picker|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|Valeur min\/Valeur max|  
|Zone d'édition|EDIT|[CEdit](../mfc/reference/cedit-class.md)|`CString`, int, UINT, long, DWORD, float, double, BYTE, short, BOOL, `COleDateTime` ou **COleCurrency**|Valeur min\/Valeur max ; certaines prennent en charge les caractères maxi|  
|Contrôle Hotkey|msctls\_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|Aucun ; contrôle uniquement|N\/A|  
|Zone de liste|LISTBOX|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|Caractères maxi|  
|Contrôle List|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|Aucun ; contrôle uniquement|N\/A|  
|Contrôle Month Calendar|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|Valeur min\/Valeur max|  
|Contrôle Progress|msctls\_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|Aucun ; contrôle uniquement|N\/A|  
|Contrôle Rich Edit 2|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|Caractères maxi|  
|Contrôle Rich Edit|RICHEDIT|`CRichEditCtrl`|`CString`|Caractères maxi|  
|Barre de défilement \(vertical ou horizontal\)|SCROLLBAR|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|Valeur min\/Valeur max|  
|Contrôle Slider|msctls\_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|Valeur min\/Valeur max|  
|Contrôle Spin|msctls\_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|Aucun ; contrôle uniquement|N\/A|  
|Contrôle Tab|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|Aucun ; contrôle uniquement|N\/A|  
|Contrôle Tree|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|Aucun ; contrôle uniquement|N\/A|  
  
## Voir aussi  
 [Ajout d'une variable membre](../ide/adding-a-member-variable-visual-cpp.md)