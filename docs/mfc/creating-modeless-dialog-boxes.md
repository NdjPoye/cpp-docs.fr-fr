---
title: "Cr&#233;ation de bo&#238;tes de dialogue non modales | Microsoft Docs"
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
  - "boîtes de dialogue MFC, créer"
  - "boîtes de dialogue MFC, non modales"
  - "boîtes de dialogue non modales, créer"
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Cr&#233;ation de bo&#238;tes de dialogue non modales
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour une boîte de dialogue non modales, vous devez fournir votre propre constructeur public dans la classe de la boîte de dialogue.  Pour créer une boîte de dialogue non modales, appelez le constructeur public puis appelez la fonction membre [Créer](../Topic/CDialog::Create.md) de l'objet DIALOG pour charger la ressource de la boîte de dialogue.  Vous pouvez appeler **Créer** soit pendant ou après l'appel de constructeur.  Si la ressource de la boîte de dialogue contient la propriété **WS\_VISIBLE**, la boîte de dialogue apparaît immédiatement.  Sinon, vous devez appeler la fonction membre [ShowWindow](../Topic/CWnd::ShowWindow.md).  
  
## Voir aussi  
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)