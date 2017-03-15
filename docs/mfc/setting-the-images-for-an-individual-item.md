---
title: "D&#233;finition des images d&#39;un &#233;l&#233;ment individuel | Microsoft Docs"
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
  - "zones de liste déroulante étendues, images"
  - "images (C++), éléments de zone de liste déroulante"
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;finition des images d&#39;un &#233;l&#233;ment individuel
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les différents types d'images utilisés par l'élément de la zone de liste modifiable étendue sont déterminés par les valeurs de `iImage`, **iSelectedImage**, et les membres **iOverlay** de la structure [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746).  Chaque valeur est l'index d'une image dans la liste des images associée du contrôle.  Par défaut, les membres sont placés sur 0, entrâinant le non\-affichage des images de l'élément par le contrôle.  Si vous souhaitez utiliser des images pour un élément spécifique, vous pouvez modifier la structure en conséquence, soit quand vous insérez l'élément de la zone de liste modifiable ou quand vous modifiez un élément de la zone de liste modifiable.  
  
## Définir l'image d'un nouvel élément  
 Si vous insérez un nouvel élément, initialisez `iImage`, **iSelectedImage**, et les membres de la structure **iOverlay** avec les valeurs appropriées puis insérez l'élément par un appel à [CComboBoxEx::InsertItem](../Topic/CComboBoxEx::InsertItem.md).  
  
 L'exemple suivant insère un nouvel élément de la zone de liste modifiable étendue \(`cbi`\) dans le contrôle de la zone de liste modifiable étendue \(`m_comboEx`\), en fournissant des indices chacun des états de l'image :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/CPP/setting-the-images-for-an-individual-item_1.cpp)]  
  
## Définir l'image d'un élément existant  
 Si vous modifiez un élément existant, vous devez utiliser le membre **mask** d'une structure de **COMBOBOXEXITEM**.  
  
#### Modifier un élément existant pour qu'il utilise des images  
  
1.  Déclarez une structure de **COMBOBOXEXITEM** et fixez le membre de données **mask** aux valeurs que vous souhaitiez modifier.  
  
2.  En utilisant cette structure, effectuez un appel à [CComboBoxEx::GetItem](../Topic/CComboBoxEx::GetItem.md).  
  
3.  Modifiez les membres **mask**, `iImage`, et **iSelectedImage** de la structure nouvellement retournée, en utilisant les valeurs appropriées.  
  
4.  Effectuez un appel à [CComboBoxEx::SetItem](../Topic/CComboBoxEx::SetItem.md), en passant dans la structure modifiée.  
  
 L'exemple suivant illustre cette procédure en permutant les images sélectionnées et désélectionnées du troisième élément étendue de la zone de liste modifiable:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/CPP/setting-the-images-for-an-individual-item_2.cpp)]  
  
## Voir aussi  
 [Utilisation de CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Contrôles](../mfc/controls-mfc.md)