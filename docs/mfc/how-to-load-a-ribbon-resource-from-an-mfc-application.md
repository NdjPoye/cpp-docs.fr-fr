---
title: "Comment : charger une ressource de ruban à partir d’une Application MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2384ff8b92936e646bc434583c6a20e07ccc85e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>Comment : charger une ressource du ruban à partir d'une application MFC
Pour utiliser la ressource de ruban dans votre application, modifiez l’application pour charger la ressource de ruban.  
  
### <a name="to-load-a-ribbon-resource"></a>Pour charger une ressource de ruban  
  
1.  Déclarez le `Ribbon Control` de l’objet dans la `CMainFrame` classe.  
  
 ```  
    CMFCRibbonBar m_wndRibbonBar;   
 ```  
  
2.  Dans `CMainFrame::OnCreate`, créer et initialiser le contrôle du ruban.  
  
 ```  
    if (!m_wndRibbonBar.Create (this))  
 {  
    return -1;  
 }  
 
    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))  
 {  
    return -1;  
 }  
 ```  
  
## <a name="see-also"></a>Voir aussi  
 [Concepteur de ruban (MFC)](../mfc/ribbon-designer-mfc.md)

