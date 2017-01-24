---
title: "Vue d&#39;ensemble du contr&#244;le RichEdit | Microsoft Docs"
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
  - "contrôles RichEdit"
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Vue d&#39;ensemble du contr&#244;le RichEdit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Si vous utilisez un contrôle RichEdit dans une boîte de dialogue \(même si votre application est basée sur SDI, MDI, ou les boîtes de dialogue\), vous devez appeler [AfxInitRichEdit](../Topic/AfxInitRichEdit.md) une fois avant que la boîte de dialogue ne s'affiche.  Un endroit usuel pour appeler cette fonction est la fonction membre `InitInstance` de votre programme.  Vous n'avez pas besoin de l'appeller chaque fois que vous affichez la boîte de dialogue, seulement la première fois.  Vous ne devez pas appeler `AfxInitRichEdit` si vous utilisez `CRichEditView`.  
  
 Les contrôles RichEdits \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) fournissent une interface de programmation pour mettre en forme le texte.  Toutefois, une application doit implémenter tous les composants d'interface utilisateur nécessaires pour rendre les opérations de mise en forme disponibles pour l'utilisateur.  Autrement dit, le contrôle RichEdit prend en charge la modification des attributs de caractères ou de paragraphe de texte sélectionné.  Quelques exemples d'attributs de caractères sont : gras, italique, la famille de polices, la taille.  Les exemples de prédicats de paragraphe incluent l'inscription, les marges, et les taquets de tabulation.  Toutefois, il vous appartient de fournir une interface utilisateur, qu'il s'agisse des boutons de la barre d'outils, des éléments de menu, ou une boîte de dialogue de format caractère.  Il existe également des fonctions pour interroger le contrôle RichEdit pour les attributs de la sélection actuelle.  Utilisez ces fonctions pour consulter les paramètres actuels pour les attributs, par exemple, définissez une marque de coche dans la commande interface utilisateur si la sélection a l'attribut de mise en forme en gras.  
  
 Pour plus d'informations sur le caractère et la mise en forme de paragraphe, consultez [Mise en forme de caractères](../mfc/character-formatting-in-rich-edit-controls.md) et [Mise en forme de paragraphe](../mfc/paragraph-formatting-in-rich-edit-controls.md) plus loin dans cette rubrique.  
  
 Les contrôles RichEdits prennent en charge environ toutes les opérations et les messages de notification utilisées avec les contrôles d'édition multilignes.  Par conséquent, les applications qui utilisent déjà les contrôles d'édition peuvent être facilement modifiées pour utiliser les contrôles RichEdits.  Les messages supplémentaires et les notifications permettent aux applications d'accéder aux fonctionnalités uniques pour les contrôles RichEdits.  Pour plus d'informations sur les contrôles d'édition, consultez [CEdit](../mfc/reference/cedit-class.md).  
  
 Pour plus d'informations sur les notifications, consultez [Notifications d'un contrôle RichEdit](../mfc/notifications-from-a-rich-edit-control.md) plus loin dans cette rubrique.  
  
## Voir aussi  
 [Utilisation de CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)