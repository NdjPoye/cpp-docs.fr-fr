---
title: "Connexion d’un Menu contextuel à votre Application | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- pop-up menus, connecting to applications
- context menus, connecting to applications
- menus, pop-up
- shortcut menus, connecting to applications
ms.assetid: 295cbf0e-6416-478e-bc3d-472fb98e0e52
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b3e74865f292adf9ba72c36e4bfe9a68e21e32f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="connecting-a-pop-up-menu-to-your-application"></a>Connexion d'un menu contextuel à votre application
### <a name="to-connect-a-pop-up-menu-to-your-application"></a>Pour connecter un menu contextuel à votre application  
  
1.  Ajoutez un gestionnaire de messages pour WM_CONTEXTMENU (par exemple). Pour plus d’informations, consultez [mappage de Messages à des fonctions](../mfc/reference/mapping-messages-to-functions.md).  
  
2.  Ajoutez le code suivant au gestionnaire de messages :  
  
    ```  
    CMenu menu;  
    VERIFY(menu.LoadMenu(IDR_MENU1));  
    CMenu* pPopup = menu.GetSubMenu(0);  
    ASSERT(pPopup != NULL);  
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());  
    ```  
  
    > [!NOTE]
    >  Le [CPoint](../atl-mfc-shared/reference/cpoint-class.md) **passé par le message gestionnaire se trouve dans les coordonnées d’écran.**  
  

  
 **Requirements**  
  
 MFC  
  
## <a name="see-also"></a>Voir aussi  
 [Création de Menus contextuels](../windows/creating-pop-up-menus.md)   
 [Éditeur de menus](../windows/menu-editor.md)   
