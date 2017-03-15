---
title: "Cr&#233;ation d&#39;un objet CToolBarCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CToolBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl (classe), créer des barres d'outils"
  - "contrôles de barre d'outils (MFC), créer"
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Cr&#233;ation d&#39;un objet CToolBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les objets de [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) contiennent plusieurs structures de données internes — une liste de bitmap de l'image de boutons, une liste de chaînes de nom de bouton, puis une liste de structures de `TBBUTTON` — qui associe une image et\/ou une chaîne avec la position, le style, l'état, et l'ID de commande du bouton.  Chacun des éléments des structures de données est indiqué par un index de base zéro.  Avant de pouvoir utiliser un objet de `CToolBarCtrl`, vous devez installer les structures de données.  Pour obtenir la liste des structures de données, consultez le [Contrôles de la barre d'outils](https://msdn.microsoft.com/en-us/library/47xcww9x.aspx) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  La liste de chaînes peut être utilisée pour les noms de bouton ; vous ne pouvez pas récupérer les chaînes de la barre d'outils.  
  
 Pour utiliser un objet `CToolBarCtrl`, vous suivrez généralement les étapes suivantes :  
  
### Pour utiliser un objet de CToolBarCtrl  
  
1.  Construit l'objet de [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md).  
  
2.  Appelez [Créer](../Topic/CToolBarCtrl::Create.md) pour créer le contrôle commun de la barre d'outils Windows et le joindre à l'objet `CToolBarCtrl`.  Si vous souhaitez des images bitmap pour les des boutons, ajoutez les images bitmap de bouton dans la barre d'outils en appelant [AddBitmap](../Topic/CToolBarCtrl::AddBitmap.md).  Si vous souhaitez des noms de chaîne pour les boutons, ajoutez des chaînes dans la barre d'outils en appelant [AddString](../Topic/CToolBarCtrl::AddString.md) et\/ou [AddStrings](../Topic/CToolBarCtrl::AddStrings.md).  Après avoir appelé `AddString` et\/ou `AddStrings`, vous devez appeler [Redimensionnement automatique](../Topic/CToolBarCtrl::AutoSize.md) pour obtenir l'affichage de la chaîne ou des chaînes.  
  
3.  Ajouter des structures de bouton dans la barre d'outils en appelant [AjouterBoutons](../Topic/CToolBarCtrl::AddButtons.md).  
  
4.  Si vous souhaitez des info\-bulles, gérez les messages de **TTN\_NEEDTEXT** dans la fenêtre propriétaire de la barre d'outils comme décrit dans [Notifications d'Info\-bulle de gestion](../mfc/handling-tool-tip-notifications.md).  
  
5.  Si vous souhaitez que vos utilisateurs puissent personnaliser la barre d'outils, traiter les messages de notification de personnalisation dans la fenêtre propriétaire comme décrit dans [Notifications de personnalisation de gestion](../mfc/handling-customization-notifications.md).  
  
## Voir aussi  
 [Utilisation de CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)