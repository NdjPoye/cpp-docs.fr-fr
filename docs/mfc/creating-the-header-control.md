---
title: "Cr&#233;ation du contr&#244;le Header | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CHeaderCtrl (classe), créer"
  - "contrôles header, créer"
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation du contr&#244;le Header
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le contrôle header n'est pas directement disponible dans l'éditeur de boîtes de dialogue \(bien que vous pouvez ajouter un contrôle de liste, ce qui inclut un contrôle header\).  
  
### Pour mettre un contrôle header dans une boîte de dialogue  
  
1.  Incorporer manuellement une variable membre de type [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) dans la classe de la boîte de dialogue.  
  
2.  Dans [OnInitDialog](../Topic/CDialog::OnInitDialog.md), créer et définir les styles pour `CHeaderCtrl`, positionnez\-les, et affichez\-les.  
  
3.  Ajout d'éléments au contrôle d'en\-tête.  
  
4.  Utilisez la fenêtre Propriétés pour mapper les fonctions de gestion dans la classe de la boîte de dialogue pour tous les messages de notifications de contrôle d'en\-tête \(voir [Mapper des messages aux fonctions](../mfc/reference/mapping-messages-to-functions.md)\).  
  
### Pour mettre un contrôle header dans une vue \(et non un CListView\)  
  
1.  Incluez un objet [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) dans la classe d'affichage.  
  
2.  Le style, la position, et l'affichage de la fenêtre de contrôle d'en\-tête dans la fonction membre [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) de la vue.  
  
3.  Ajout d'éléments au contrôle d'en\-tête.  
  
4.  Utilisez la fenêtre Propriétés pour mapper les fonctions de gestion dans la classe de la vue pour tous les messages de notifications de contrôle d'en\-tête \(voir [Mapper des messages aux fonctions](../mfc/reference/mapping-messages-to-functions.md)\).  
  
 Dans l'un et l'autre cas, l'objet de contrôle incorporé est créé lorsque la vue ou l'objet du dialogue est créé.  Vous devez appeler [CHeaderCtrl::Create](../Topic/CHeaderCtrl::Create.md) pour créer le point de contrôle.  Pour positionner le contrôle, appelez [CHeaderCtrl::Layout](../Topic/CHeaderCtrl::Layout.md) pour déterminer la taille initiale du contrôle et les placer et [SetWindowPos](../Topic/CWnd::SetWindowPos.md) pour définir la position souhaitée.  Ajoutez ensuite des éléments comme décrit dans [Ajout d'éléments dans le contrôle header](../mfc/adding-items-to-the-header-control.md).  
  
 Pour plus d'informations, consultez  [Création de contrôles d'en\-tête](http://msdn.microsoft.com/library/windows/desktop/bb775238) dans le [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Voir aussi  
 [Utilisation de CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)