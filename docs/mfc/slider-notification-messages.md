---
title: "Messages de notification du Slider | Microsoft Docs"
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
  - "CSliderCtrl (classe), notifications"
  - "messages, notification"
  - "notifications, CSliderCtrl"
  - "contrôles Slider, messages de notification"
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Messages de notification du Slider
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un curseur notifie la fenêtre parente d'actions utilisateur en envoyant des messages aux parents `WM_HSCROLL` ou `WM_VSCROLL`, selon l'orientation du curseur.  Pour traiter ces messages, ajouter des gestionnaires des messages de `WM_HSCROLL` et de `WM_VSCROLL` à la fenêtre parente.  Les fonctions membres de [OnHScroll](../Topic/CWnd::OnHScroll.md) et de [OnVScroll](../Topic/CWnd::OnVScroll.md) recevront un code de notification, la position du curseur, et un pointeur vers l'objet de [CSliderCtrl](../mfc/reference/csliderctrl-class.md).  Notez que le pointeur est de type **CScrollBar \*** bien qu'il indique un objet de `CSliderCtrl`.  Vous devrez peut\-être cataloguer ce pointeur si vous manipulez le curseur.  
  
 Au lieu d'utiliser les codes de notification de la barre de défilement, les curseurs envoient un ensemble différent de codes de notification.  Un curseur envoie des notifications de **TB\_BOTTOM**, de **TB\_LINEDOWN**, de **TB\_LINEUP**, et de **TB\_TOP** uniquement lorsque l'utilisateur interagit avec un curseur à l'aide de le clavier.  Les messages de notification de **TB\_THUMBPOSITION** et de **TB\_THUMBTRACK** sont envoyés uniquement lorsque l'utilisateur utilise la souris.  Les codes de notification de **TB\_ENDTRACK**, de **TB\_PAGEDOWN**, et de **TB\_PAGEUP** sont envoyés dans les deux cas.  
  
 Le tableau suivant répertorie les messages de notification de curseur et les événements \(codes de clé virtuelle ou événements de la souris\) qui causent l'envoi notifications. \(Pour obtenir la liste de codes touche virtuelle standard, consultez Winuser.h.\)  
  
|messages de notification|Événement qui provoque la notification à envoyer|  
|------------------------------|------------------------------------------------------|  
|**TB\_BOTTOM**|**VK\_END**|  
|**TB\_ENDTRACK**|`WM_KEYUP` \(l'utilisateur a levé une clé qui a envoyé le code de clé virtuelle pertinent\)|  
|**TB\_LINEDOWN**|**VK\_RIGHT** ou **VK\_DOWN**|  
|**TB\_LINEUP**|**VK\_LEFT** ou **VK\_UP**|  
|**TB\_PAGEDOWN**|**VK\_NEXT** \(l'utilisateur a cliqué sur le canal sous le curseur ou à sa droite\)|  
|**TB\_PAGEUP**|**VK\_PRIOR** \(l'utilisateur a cliqué sur le canal au\-dessus ou à gauche du curseur\)|  
|**TB\_THUMBPOSITION**|`WM_LBUTTONUP` après un message de notification de **TB\_THUMBTRACK**|  
|**TB\_THUMBTRACK**|Déplacement du curseur \(l'utilisaeur a fait glisser le curseur\)|  
|**TB\_TOP**|**VK\_HOME**|  
  
## Voir aussi  
 [Utilisation de CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)