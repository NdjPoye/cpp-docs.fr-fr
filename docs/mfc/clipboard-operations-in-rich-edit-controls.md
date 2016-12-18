---
title: "Op&#233;rations du Presse-papiers dans les contr&#244;les RichEdit | Microsoft Docs"
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
  - "Presse-papiers, opérations dans CRichEditCtrl"
  - "opérations de copie dans les contrôles RichEdit"
  - "CRichEditCtrl (classe), opérations du Presse-papiers"
  - "CRichEditCtrl (classe), opération de collage"
  - "opération de coupe dans la classe CRichEditCtrl"
  - "coller les données du Presse-papiers"
  - "contrôles RichEdit, opérations du Presse-papiers"
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rations du Presse-papiers dans les contr&#244;les RichEdit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Votre application peut coller le contenu du presse\-papiers dans un contrôle RichEdit \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) à l'aide du meilleur format de presse\-papiers disponible ou un format spécifique du presse\-papiers.  Vous pouvez également déterminer si un contrôle RichEdit est capable de coller un format de presse\-papiers.  
  
 Vous pouvez couper ou copier le contenu de la sélection actuelle à l'aide de la fonction membre [Copier](../Topic/CRichEditCtrl::Copy.md) ou [Couper](../Topic/CRichEditCtrl::Cut.md).  De même, vous pouvez coller le contenu du presse\-papiers dans un contrôle RichEdit à l'aide de la fonction membre [Coller](../Topic/CRichEditCtrl::Paste.md).  Le contrôle colle le premier format disponible qu'il identifie, qui est supposé être au format le plus descriptif.  
  
 Pour coller un format spécifique du presse\-papiers, il est possible d'utiliser la fonction membre [PasteSpecial](../Topic/CRichEditCtrl::PasteSpecial.md).  Cette fonction est utile pour les applications dont une commande particulière de collage qui permet à l'utilisateur de sélectionner le format du presse\-papiers.  Vous pouvez utiliser la fonction membre [CanPaste](../Topic/CRichEditCtrl::CanPaste.md) pour déterminer si un format spécifique est identifié par le contrôle.  
  
 Vous pouvez également utiliser `CanPaste` pour déterminer si n'importe quel format du presse\-papiers disponible est identifié par un contrôle RichEdit.  Cette fonction est utile dans le gestionnaire `OnInitMenuPopup`.  Une application peut activer ou griser son Collage selon si le contrôle peut coller tout format disponible ou non.  
  
 Les contrôles RichEdits comprennent deux formats du presse\-papiers : le format Rich Text Format et un format appelé RichEdit Text et Objets.  Une application peut stocker ces formats à l'aide de la fonction [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049), en spécifiant les valeurs de **CF\_RTF** et de **CF\_RETEXTOBJ**.  
  
## Voir aussi  
 [Utilisation de CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)