---
title: TOOLTIPTEXT (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TOOLTIPTEXT
dev_langs: C++
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- tool tips [MFC], notifications
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: becbdcfcc6dbd26ae3095de098d12dbc078530cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="tooltiptext-structure"></a>TOOLTIPTEXT, structure
Une écriture votre [Gestionnaire de notification de conseil outil](../mfc/handling-ttn-needtext-notification-for-tool-tips.md), vous devez utiliser le `TOOLTIPTEXT` structure. Les membres de le `TOOLTIPTEXT` structure sont :  
  
 `typedef struct {`  
  
 `NMHDR     hdr;        // required for all WM_NOTIFY messages`  
  
 `LPTSTR    lpszText;   // see below`  
  
 `TCHAR     szText[80]; // buffer for tool tip text`  
  
 `HINSTANCE hinst;      // see below`  
  
 `UINT      uflags;     // flag indicating how to interpret the`  
  
 `// idFrom member of the NMHDR structure`  
  
 `// that is included in the structure`  
  
 `} TOOLTIPTEXT, FAR *LPTOOLTIPTEXT;`  
  
 `hdr`  
 Identifie l’outil qui a besoin de texte. Le seul membre de cette structure, que vous devrez peut-être est l’ID de commande. du contrôle ID de commande du contrôle sera dans la `idFrom` membre de la `NMHDR` structure, accédé via la syntaxe `hdr.idFrom`. Consultez [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) pour en savoir plus sur les membres de le `NMHDR` structure.  
  
 `lpszText`  
 Adresse d’une chaîne qui recevra le texte pour un outil.  
  
 `szText`  
 Mémoire tampon qui reçoit le texte info-bulle. Une application peut copier le texte à cette mémoire tampon en guise d’alternative à la spécification d’une adresse de la chaîne.  
  
 `hinst`  
 Handle de l’instance qui contient une chaîne à utiliser en tant que le texte info-bulle. Si `lpszText` est l’adresse du texte info-bulle, ce membre a la valeur NULL.  
  
 Lorsque vous gérez le `TTN_NEEDTEXT` notification s’affiche, spécifiez la chaîne à afficher dans une des manières suivantes :  
  
-   Copiez le texte dans la mémoire tampon spécifiée par le `szText` membre.  
  
-   Copiez l’adresse de la mémoire tampon qui contient le texte à le `lpszText` membre.  
  
-   Copiez l’identificateur d’une ressource de chaîne pour le `lpszText` membre et copie le handle de l’instance qui contient la ressource à le `hinst` membre.  
  
## <a name="see-also"></a>Voir aussi  
 [Info-bulles dans les fenêtres non dérivées de CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

