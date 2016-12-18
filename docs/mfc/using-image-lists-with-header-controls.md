---
title: "Utilisation de listes d&#39;images avec des contr&#244;les Header | Microsoft Docs"
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
  - "CHeaderCtrl (classe), listes d'images"
  - "contrôles header, listes d'images"
  - "listes d'images (C++), contrôles header"
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de listes d&#39;images avec des contr&#244;les Header
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les éléments d'en\-tête ont la possibilité d'afficher une image dans un élément d'en\-tête.  Cette image, stockée dans une liste d'image associée, est de 16 x 16 pixels et a les mêmes caractéristiques que les images d'icônes utilisées dans une liste de contrôle de vue.  Pour implémenter ce comportement avec succès, vous devez d'abord créer et démarrer la liste des images, associer la liste avec le contrôle de l'en\-tête, puis modifier les attributs de l'élément d'en\-tête qui affiche l'image.  
  
 La procédure suivante montre ces informations, avec un pointeur à un contrôle d'en\-tête \(`m_pHdrCtrl`\) et un pointeur vers une liste des images \(`m_pHdrImages`\).  
  
### Pour afficher une image dans un élément d'en\-tête  
  
1.  Construisez une liste d'images \(ou utilisez un objet liste des images existant\) à l'aide du constructeur [CImageList](../mfc/reference/cimagelist-class.md), en enregistrant le pointeur résultant.  
  
2.  Initialise un nouvel objet liste des images en appelant [CImageList::Create](../Topic/CImageList::Create.md).  La ligne de code suivante donne une illustration pour ce choix.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/CPP/using-image-lists-with-header-controls_1.cpp)]  
  
3.  Ajouter des images pour chaque élément d'en\-tête.  Le code suivant ajoute deux images prédéfinies.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/CPP/using-image-lists-with-header-controls_2.cpp)]  
  
4.  Associez la liste des images au contrôle header par un appel à [CHeaderCtrl::SetImageList](../Topic/CHeaderCtrl::SetImageList.md).  
  
5.  Modifiez l'élément d'en\-tête pour afficher une image à la liste des images associée.  L'exemple suivant affecte la première image, de `m_phdrImages`, au premier élément d'en\-tête, `m_pHdrCtrl`.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/CPP/using-image-lists-with-header-controls_3.cpp)]  
  
 Pour plus d'informations sur les valeurs des paramètre utilisées, consultez [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md).  
  
> [!NOTE]
>  Il est possible d'avoir plusieurs commandes en utilisant la même liste des images.  Par exemple, dans un contrôle de liste de vue standard, il peut y avoir une liste des images \(d'images de 16 x 16 pixels\) utilisée par la vue de petite icône d'un contrôle de liste de vue et les éléments d'en\-tête de contrôle de liste de vue.  
  
## Voir aussi  
 [Utilisation de CHeaderCtrl](../mfc/using-cheaderctrl.md)