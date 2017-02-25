---
title: "Fonctions membres de contr&#244;le Slider | Microsoft Docs"
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
  - "CSliderCtrl (classe), méthodes"
  - "contrôles Slider, fonctions membres"
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Fonctions membres de contr&#244;le Slider
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An application can call the slider control's member functions to retrieve information about the slider control \([CSliderCtrl](../mfc/reference/csliderctrl-class.md)\) and to change its characteristics.  
  
 To retrieve the position of the slider \(that is, the value the user has chosen\), use the [GetPos](../Topic/CSliderCtrl::GetPos.md) member function.  To set the position of the slider, use the [SetPos](../Topic/CSliderCtrl::SetPos.md) member function.  At any time you can use the `VerifyPos` member function to make sure that the slider is between the minimum and maximum values.  
  
 The range of a slider control is the set of contiguous values that the slider control can represent.  Most applications use the [SetRange](../Topic/CSliderCtrl::SetRange.md) member function to set the range of a slider control when it is first created.  Applications can dynamically alter the range after the slider control has been created by using the [SetRangeMax](../Topic/CSliderCtrl::SetRangeMax.md) and [SetRangeMin](../Topic/CSliderCtrl::SetRangeMin.md) member functions.  An application that allows the range to be changed dynamically typically retrieves the final range settings when the user has finished working with the slider control.  To retrieve these settings, use the [GetRange](../Topic/CSliderCtrl::GetRange.md), [GetRangeMax](../Topic/CSliderCtrl::GetRangeMax.md), and [GetRangeMin](../Topic/CSliderCtrl::GetRangeMin.md) member functions.  
  
 An application can use the `TBS_AUTOTICKS` style to have a slider control's tick marks displayed automatically.  If an application needs to control the position or frequency of the tick marks, however, a number of member functions can be used.  
  
 To set the position of a tick mark, an application can use the [SetTic](../Topic/CSliderCtrl::SetTic.md) member function.  The [SetTicFreq](../Topic/CSliderCtrl::SetTicFreq.md) member function allows an application to set tick marks that appear at regular intervals in the slider control's range.  For example, the application can use this member function to display only 10 tick marks in a range of 1 through 100.  
  
 To retrieve the index in the range corresponding to a tick mark, use the [GetTic](../Topic/CSliderCtrl::GetTic.md) member function.  The [GetTicArray](../Topic/CSliderCtrl::GetTicArray.md) member function retrieves an array of these indices.  To retrieve the position of a tick mark, in client coordinates, use the [GetTicPos](../Topic/CSliderCtrl::GetTicPos.md) member function.  An application can retrieve the number of tick marks by using the [GetNumTics](../Topic/CSliderCtrl::GetNumTics.md) member function.  
  
 The [ClearTics](../Topic/CSliderCtrl::ClearTics.md) member function removes all of a slider control's tick marks.  
  
 A slider control's line size determines how far the slider moves when an application receives a **TB\_LINEDOWN** or **TB\_LINEUP** notification message.  Similarly, the page size determines the response to the **TB\_PAGEDOWN** and **TB\_PAGEUP** notification messages.  Applications can retrieve and set the line and page size values by using the [GetLineSize](../Topic/CSliderCtrl::GetLineSize.md), [SetLineSize](../Topic/CSliderCtrl::SetLineSize.md), [GetPageSize](../Topic/CSliderCtrl::GetPageSize.md), and [SetPageSize](../Topic/CSliderCtrl::SetPageSize.md) member functions.  
  
 An application can use member functions to retrieve the dimensions of a slider control.  The [GetThumbRect](../Topic/CSliderCtrl::GetThumbRect.md) member function retrieves the bounding rectangle for the slider.  The [GetChannelRect](../Topic/CSliderCtrl::GetChannelRect.md) member function retrieves the bounding rectangle for the slider control's channel. \(The channel is the area over which the slider moves and which contains the highlight when a range is selected.\)  
  
 If a slider control has the `TBS_ENABLESELRANGE` style, the user can select a range of contiguous values from it.  A number of member functions allow the selection range to be adjusted dynamically.  The [SetSelection](../Topic/CSliderCtrl::SetSelection.md) member function sets the starting and ending positions of a selection.  When the user has finished setting a selection range, an application can retrieve the settings by using the [GetSelection](../Topic/CSliderCtrl::GetSelection.md) member function.  To clear a user's selection, use the [ClearSel](../Topic/CSliderCtrl::ClearSel.md) member function.  
  
## Voir aussi  
 [Utilisation de CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)