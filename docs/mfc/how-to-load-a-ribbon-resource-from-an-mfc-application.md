---
title: "Comment&#160;: charger une ressource du ruban &#224; partir d&#39;une application MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ressource du ruban, charger"
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: charger une ressource du ruban &#224; partir d&#39;une application MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour utiliser la ressource ruban dans votre application, modifiez l'application pour charger la ressource ruban.  
  
### Charger une ressource ruban  
  
1.  Déclarez l'objet `Ribbon Control` dans la classe`CMainFrame`.  
  
    ```  
    CMFCRibbonBar m_wndRibbonBar;   
    ```  
  
2.  Dans `CMainFrame::OnCreate`, créez et initialisez le contrôle ruban.  
  
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
  
## Voir aussi  
 [Concepteur de ruban \(MFC\)](../mfc/ribbon-designer-mfc.md)