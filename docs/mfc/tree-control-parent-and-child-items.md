---
title: "&#201;l&#233;ments parents et enfants du contr&#244;le d&#39;arborescence | Microsoft Docs"
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
  - "éléments enfants dans le contrôle d'arborescence"
  - "CTreeCtrl (classe), éléments parents et enfants"
  - "éléments parents dans CTreeCtrl"
  - "contrôles d'arborescence, éléments parents et enfants"
ms.assetid: abcea1e4-fe9b-40d9-86dc-1db235f8f103
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# &#201;l&#233;ments parents et enfants du contr&#244;le d&#39;arborescence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Tout élément dans un contrôle d'arborescence \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) peut comporter une liste des sous\-éléments, qui sont appelés éléments enfants, qui lui sont associés.  Un élément qui a un ou plusieurs éléments enfants est appelé un élément parent.  Un élément enfant s'affiche sous l'élément parent et est mis en retrait pour l'identifier comme subordonnés au parent.  Un élément qui n'a aucun parent est en haut de la hiérarchie et est appelé un élément racine.  
  
 À tout moment, l'état d'une liste d'éléments parents d'élément enfants peut être développé ou réduit.  Lorsque l'état est développé, les éléments enfants apparaissent sous l'élément parent.  Lorsqu'il est réduit, les éléments enfants ne sont pas affichés.  La liste bascule automatiquement entre les états développés ou réduits lorsque l'utilisateur double clique sur l'élément parent ou, si le parent a le style **TVS\_HASBUTTONS**, lorsque l'utilisateur clique sur le bouton associé à l'élément parent.  Une application peut augmenter ou réduire les éléments enfants à l'aide de la fonction membre [Développer](../Topic/CTreeCtrl::Expand.md).  
  
 Vous ajoutez un élément à un contrôle d'arborescence en appelant la fonction membre [InsertItem](../Topic/CTreeCtrl::InsertItem.md).  Cette fonction retourne un handle du type de **HTREEITEM**, qui identifie l'élément.  En ajoutant un élément, vous devez spécifier le descripteur de l'élément parent du nouvel élément.  Si vous spécifiez **NULL** ou la valeur **TVI\_ROOT** au lieu d'un descripteur parent de l'élément dans la structure [TVINSERTSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb773452) ou le paramètre `hParent`, l'élément est ajouté en tant qu'élément racine.  
  
 Un contrôle d'arborescence envoie un message de notification [TVN\_ITEMEXPANDING](http://msdn.microsoft.com/library/windows/desktop/bb773537) lorsque l'élément parent d'une liste d'éléments enfants est sur le point d'être développée ou réduite.  La notification vous permet d'empêcher la modification ou la définition de tous les attributs de l'élément parent qui dépendent de l'état de la liste des éléments enfants.  Après avoir modifié l'état de la liste, l'arborescence envoie un message de notification [TVN\_ITEMEXPANDED](http://msdn.microsoft.com/library/windows/desktop/bb773533).  
  
 Lorsqu'une liste d'éléments enfants est développée, elle est mise en retrait par rapport à l'élément parent.  Vous pouvez définir la quantité de mise en retrait à l'aide de la fonction membre [SetIndent](../Topic/CTreeCtrl::SetIndent.md) ou récupérer la valeur actuelle à l'aide de la fonction membre [GetIndent](../Topic/CTreeCtrl::GetIndent.md).  
  
## Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)