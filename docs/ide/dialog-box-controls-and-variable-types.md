---
title: "Contrôles de boîte de dialogue et Types de variables | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- dialog box controls, member variables
- dialog box controls, variable types
- variables, dialog box control member variables
ms.assetid: f9cd9cea-45a6-4349-8358-e5efbcdcff76
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 744b9da2db456a72ed386806d8a4aa34c5942f69
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-box-controls-and-variable-types"></a>Contrôles de boîtes de dialogue et types de variables
Vous pouvez utiliser la [Assistant Ajout de Variable membre](../ide/add-member-variable-wizard.md) pour ajouter une variable membre à un contrôle de boîte de dialogue créé à l’aide de MFC. Le type de contrôle pour lequel vous ajoutez la variable membre détermine les options qui apparaissent dans la boîte de dialogue.  
  
 Le tableau suivant décrit tous les types de contrôle de boîte de dialogue pris en charge dans MFC et [boîte de dialogue Éditeur](../windows/dialog-editor.md)et leurs types et valeurs disponibles.  
  
|Contrôle|Type du contrôle|Type de variable de contrôle|Type de variable de valeur|Valeurs min/max (type valeur uniquement)|  
|-------------|------------------|---------------------------|-------------------------|-----------------------------------------|  
|Contrôle Animation|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|None ; contrôle uniquement|N/A|  
|Bouton|BOUTON|[CButton](../mfc/reference/cbutton-class.md)|None ; contrôle uniquement|N/A|  
|Case à cocher|VÉRIFICATION|[CButton](../mfc/reference/cbutton-class.md)|**BOOL**|Valeur de valeur max. de min|  
|Zone de liste modifiable|ZONE DE LISTE DÉROULANTE|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|Caractères max|  
|Contrôle date time picker|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|Valeur de valeur max. de min|  
|Zone d’édition|EDITION|[CEdit](../mfc/reference/cedit-class.md)|`CString`, int, UINT, long, DWORD, float, double, BYTE, bref, BOOL, `COleDateTime`, ou **COleCurrency**|Valeur de valeur max. de min ; certains caractères au maximum prise en charge|  
|Contrôle de touche d’accès rapide|msctls_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|None ; contrôle uniquement|N/A|  
|Zone de liste|ZONE DE LISTE|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|Caractères max|  
|Contrôle List|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|None ; contrôle uniquement|N/A|  
|Contrôle Month Calendar|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|Valeur de valeur max. de min|  
|Contrôle Progress|msctls_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|None ; contrôle uniquement|N/A|  
|Contrôle Rich Edit 2|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|Caractères max|  
|Contrôle Rich Edit|RICHEDIT|`CRichEditCtrl`|`CString`|Caractères max|  
|Barre de défilement (verticale ou horizontale|BARRE DE DÉFILEMENT|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|Valeur de valeur max. de min|  
|Contrôle Slider|msctls_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|Valeur de valeur max. de min|  
|Contrôle Spin|msctls_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|None ; contrôle uniquement|N/A|  
|Contrôle Tab|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|None ; contrôle uniquement|N/A|  
|Contrôle Tree|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|None ; contrôle uniquement|N/A|  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout d’une Variable membre](../ide/adding-a-member-variable-visual-cpp.md)