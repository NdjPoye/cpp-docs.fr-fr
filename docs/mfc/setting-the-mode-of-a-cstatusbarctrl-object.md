---
title: "D&#233;finition du mode d&#39;un objet CStatusBarCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl (classe), modes simple et non simple"
  - "IsSimple (méthode), utilisation"
  - "mode non simple et contrôles de barre d'état"
  - "SetSimple (méthode)"
  - "mode simple et contrôles de barre d'état"
  - "contrôles de barre d'état, modes simple et non simple"
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# D&#233;finition du mode d&#39;un objet CStatusBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il existe deux modes pour un objet `CStatusBarCtrl`: simple et nonsimple.  Dans la majorité des cas, la vérification de la barre d'état aura une ou plusieurs parties, avec le texte et éventuellement une icône ou des icônes.  On parle de mode nonsimple.  Pour plus d'informations sur ce mode, consultez [Initialisation des parties d'un objet de CStatusBarCtrl](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).  
  
 Toutefois, il existe des cas où vous devez afficher une simple ligne de texte.  Dans ce cas, le mode simple suffit à vos besoins.  Pour modifier le mode de l'objet `CStatusBarCtrl` pour l'attribuer à simple, effectuez un appel à la fonction membre [SetSimple](../Topic/CStatusBarCtrl::SetSimple.md).  Une fois que le contrôle de la barre d'état est en mode simple, définissez le texte en appelant la fonction membre **SetText**, en passant 255 comme valeur pour le paramètre **nPane**.  
  
 Vous pouvez utiliser la fonction [IsSimple](../Topic/CStatusBarCtrl::IsSimple.md) pour déterminer dans quel mode l'objet `CStatusBarCtrl` se trouve.  
  
> [!NOTE]
>  Si l'objet de la barre d'état est modifié de nonsimple à simple, ou vice versa, la fenêtre est immédiatement redessinée et, si tel est le cas, toutes les parties définies automatiquement restaurées.  
  
## Voir aussi  
 [Utilisation de CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)