---
title: "Vue d&#39;ensemble des &#233;tats d&#39;&#233;l&#233;ment de contr&#244;le d&#39;arborescence | Microsoft Docs"
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
  - "CTreeCtrl (classe), états de l'élément"
  - "états, CTreeCtrl (éléments)"
  - "contrôles d'arborescence, états de l'élément (vue d'ensemble)"
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Vue d&#39;ensemble des &#233;tats d&#39;&#233;l&#233;ment de contr&#244;le d&#39;arborescence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chaque élément dans un contrôle d'arborescence \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) a un état actuel.  Par exemple, un élément peut être sélectionné, desactivé, développé, et ainsi de suite.  Dans la plupart des cas, l'arborescence définit automatiquement l'état d'un élément de sorte à refléter toutes les actions de l'utilisateur, telles que la sélection d'un élément.  Toutefois, vous pouvez également définir l'état d'un élément à l'aide de la fonction membre d' [SetItemState](../Topic/CTreeCtrl::SetItemState.md) et récupérer l'état actuel d'un élément à l'aide de la fonction membre d' [GetItemState](../Topic/CTreeCtrl::GetItemState.md).  Pour obtenir une liste complète des états des éléments, consultez [Constantes de contrôle arborescence](http://msdn.microsoft.com/library/windows/desktop/bb759985) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 L'état actuel d'un élément est spécifié par le paramètre d' `nState`.  Un contrôle d'arborescence peut modifier l'état d'un élément de sorte à refléter une action d'utilisateur, telle que sélectionner l'élément ou définir le focus sur l'élément.  En outre, une application peut modifier l'état d'un élément pour désactiver ou masquer l'élément ou pour spécifier une image de recouvrement ou d'état.  
  
 Lorsque vous définissez ou modifiez l'état d'un élément, le paramètre d' `nStateMask` spécifie pour quel état les bits sont à définir, et le paramètre d' `nState` contient les nouvelles valeurs pour ces bits.  Par exemple, l'exemple suivant modifie l'état actuel d'un élément parent \(spécifié par `hParentItem`\) dans un objet d' `CTreeCtrl` \(`m_treeCtrl`\) à **TVIS\_EXPANDPARTIAL**:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/CPP/tree-control-item-states-overview_1.cpp)]  
  
 Un autre exemple de modification d'état serait de définir l'image de recouvrement d'un élément.  Pour ce faire, `nStateMask` doit inclure la valeur d' `TVIS_OVERLAYMASK`, et `nState` doit inclure l'index de base un de l'image de recouvrement déplacée à gauche de huit bits en utilisant la macro d' [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408).  L'index peut être 0 pour spécifier qu'il n'y a aucune image de recouvrement.  L'image de revcouvrement doit avoir été ajoutée à la liste de contrôle d'arborescence d'images de recouvrement par un précédent appel à la fonction d' [CImageList::SetOverlayImage](../Topic/CImageList::SetOverlayImage.md).  La fonction spécifie l'index de base un de l'image à ajouter; il s'agit de l'index utilisé avec la macro d' **INDEXTOOVERLAYMASK**.  Un contrôle d'arborescence peut contenir jusqu'à quatre images de recouvrement.  
  
 Pour définir l'image de l'état d'un élément, `nStateMask` doit inclure la valeur d' `TVIS_STATEIMAGEMASK`, et `nState` doit inclure l'index de base un de l'image d'état déplacée à gauche de 12 bits en utilisant la macro d' [INDEXTOSTATEIMAGEMASK](http://msdn.microsoft.com/library/windows/desktop/bb775597).  L'index peut être 0 pour spécifier qu'il n'y a aucune image d'état.  Pour plus d'informations sur les images de recouvrement et d'état, consultez [Listes d'images de contrôle tree](../mfc/tree-control-image-lists.md).  
  
## Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)