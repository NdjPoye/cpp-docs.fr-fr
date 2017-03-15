---
title: "Styles de contr&#244;le d&#39;arborescence | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TVS_SINGLEEXPAND"
  - "TVS_LINESATROOT"
  - "TVS_HASBUTTONS"
  - "TVS_NOTOOLTIPS"
  - "TVS_HASLINES"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl (classe), styles"
  - "styles, CTreeCtrl"
  - "styles, contrôle d'arborescence"
  - "contrôles d'arborescence, styles"
  - "TVS_EDITLABELS"
  - "TVS_HASBUTTONS"
  - "TVS_HASLINES"
  - "TVS_LINESATROOT"
  - "TVS_NOTOOLTIPS"
  - "TVS_SINGLEEXPAND"
ms.assetid: f43faebd-a355-479e-888a-bf0673d5e1b4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Styles de contr&#244;le d&#39;arborescence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les styles de contrôle tree \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\)régissent les aspects de l'apparence d'un contrôle d'arborescence.  Vous définissez les styles initiale lorsque vous créez l'arborescence.  Vous pouvez extraire et modifier les styles après avoir créé un contrôle d'arborescence à l'aide de les fonctions Windows pour [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) et d'[SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591), en spécifiant **GWL\_STYLE** pour le paramètre d'`nIndex`.  Pour obtenir la liste complète des styles, consultez l'[Styles de contrôle arborescence](http://msdn.microsoft.com/library/windows/desktop/bb760013) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Le style de **TVS\_HASLINES** améliore les performances graphique d'une hiérarchie d'arborescence lors de le traçage des lignes qui lient les éléments enfants sous leur élément parent correspondant.  Ce style ne contient pas de liens des éléments à la racine de la hiérarchie.  Pour ce faire, vous devez combiner les styles de **TVS\_HASLINES** et de **TVS\_LINESATROOT**.  
  
 L'utilisateur peut augmenter ou diminuer la liste parente d'un élément d'éléments enfants en double\-cliquant sur l'élément parent.  Un contrôle d'arborescence qui contient le style de **TVS\_SINGLEEXPAND** provoque l'élément sélectionné pour développer et l'élément est désélectionné pour s'effondrer.  Si la souris est utilisée pour sélectionner une fois l'élément et l'élément est fermé, il sera développé.  Si l'élément sélectionné est cliqué une fois quand il est ouvert, elle sera réduite.  
  
 Un contrôle d'arborescence qui contient le style de **TVS\_HASBUTTONS** ajoute un bouton à gauche de chaque élément parent.  L'utilisateur peut cliquer sur le bouton pour augmenter ou réduire les éléments enfants comme alternative à double\-cliquez sur l'élément parent.  **TVS\_HASBUTTONS** n'ajoute pas de boutons aux éléments de niveau supérieur de la hiérarchie.  Pour ce faire, vous devez combiner **TVS\_HASLINES**, **TVS\_LINESATROOT**, et **TVS\_HASBUTTONS**.  
  
 Le style de **TVS\_EDITLABELS** permet à l'utilisateur modifie les noms des éléments du contrôle d'arborescence.  Pour plus d'informations sur les noms de modification, consultez l'[Modification du nom de contrôle tree](../mfc/tree-control-label-editing.md) plus loin dans cette rubrique.  
  
 Le style de **TVS\_NOTOOLTIPS** désactive la configuration automatique d'info\-bulle de contrôle arborescence.  Cette fonctionnalité affiche automatiquement une info\-bulle, qui contient le titre de l'élément dans le curseur de la souris, si le titre entier n'est pas visible.  
  
## Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)