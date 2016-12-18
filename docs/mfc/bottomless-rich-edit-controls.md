---
title: "Contr&#244;les RichEdit sans marge inf&#233;rieure | Microsoft Docs"
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
  - "contrôles RichEdit sans marge inférieure"
  - "CRichEditCtrl (classe), sans marge inférieure"
  - "contrôles RichEdit, sans marge inférieure"
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les RichEdit sans marge inf&#233;rieure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Votre application peut redimensionner un contrôle d'édition riche \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) si nécessaire afin qu'il soit toujours de la même taille que son contenu.  Un contrôle d'édition riche prend en charge cette fonctionnalité soi\-disant « sans fond » en envoyant à sa fenêtre parente un message de notification d' [EN\_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787983) chaque fois que la taille de son contenu varie.  
  
 Lors du traitement du message de notification d' **EN\_REQUESTRESIZE**, une application doit redimensionner le contrôle des dimensions dans la structure spécifiée d' [REQRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787950).  Une application peut également déplacer toutes les informations à côté du contrôle pour contenir le changement du contrôle de la hauteur.  Pour redimensionner le contrôle, vous pouvez utiliser la fonction [SetWindowPos](../Topic/CWnd::SetWindowPos.md)d' `CWnd`.  
  
 Vous pouvez forcer un contrôle d'édition riche sans fond à envoyer un message de notification d' **EN\_REQUESTRESIZE** à l'aide de la fonction membre d' [RequestResize](../Topic/CRichEditCtrl::RequestResize.md).  Ce message peut être utile dans le gestionnaire d' [OnSize](../Topic/CWnd::OnSize.md).  
  
 Pour recevoir les messages de notification d' **EN\_REQUESTRESIZE**, vous devez autoriser la notification à l'aide de la fonction membre d' `SetEventMask`.  
  
## Voir aussi  
 [Utilisation de CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)