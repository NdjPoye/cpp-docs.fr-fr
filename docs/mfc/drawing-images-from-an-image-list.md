---
title: "Dessin d&#39;images &#224; partir d&#39;une liste d&#39;images | Microsoft Docs"
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
  - "CImageList (classe), dessiner des images"
  - "dessiner, images à partir de listes d'images"
  - "listes d'images (C++), dessiner des images"
  - "images (C++), dessin"
ms.assetid: 2f6063fb-1c28-45f8-a333-008c064db11c
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Dessin d&#39;images &#224; partir d&#39;une liste d&#39;images
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour dessiner une image, utilisez la fonction membre d' [CImageList::Draw](../Topic/CImageList::Draw.md).  Spécifiez un pointeur vers un objet de contexte de périphérique, l'index de l'image à dessiner, l'emplacement dans le contexte de périphérique où dessiner l'image, et un jeu d'indicateurs pour indiquer le style de dessin.  
  
 Lorsque vous spécifiez le style d' `ILD_TRANSPARENT`, **Dessiner** utilise un processus en deux étapes pour dessiner une image masquée.  En premier lieu, elle effectue une opération AND logique\- sur les bits de l'image et les bits du masque.  Puis elle exécute une opération de logique\- XOR sur les résultats de la première opération et les bits d'arrière\-plan du contexte de destination de périphérique.  Ce processus crée des zones transparentes dans l'image résultante; autrement dit, chaque bit blanc dans le masque rend le bit correspondant dans l'image résultante transparent.  
  
 Avant de dessiner une image masquée sur un arrière\-plan de couleur unie, vous devez utiliser la fonction membre d' [SetBkColor](../Topic/CImageList::SetBkColor.md) pour définir la couleur d'arrière\-plan de la liste des images à la même couleur que la destination.  Définir la couleur élimine le besoin de créer des zones transparentes dans l'image et permet à **Dessiner** de copier simplement l'image au contexte de destination de périphérique, ce qui entraîne une augmentation significative des performances.  Pour ajouter l'image, spécifiez le style d' `ILD_NORMAL` lorsque vous appelez **Dessiner**.  
  
 Vous pouvez définir la couleur d'arrière\-plan pour une liste d'images masquées \([CImageList](../mfc/reference/cimagelist-class.md)\) à tout moment afin qu'elle dessine correctement sur n'importe quel arrière\-plan uni.  Définir la couleur d'arrière\-plan à `CLR_NONE` entraîne que les images à ajouter soient dessinées transparentes par défaut.  Pour récupérer la couleur d'arrière\-plan d'une liste d'images, utilisez la fonction membre d' [GetBkColor](../Topic/CImageList::GetBkColor.md).  
  
 Les styles d' `ILD_BLEND25` et d' `ILD_BLEND50` font trembler l'image avec la couleur de surbrillance du système.  Ces styles sont utiles si vous utilisez une image masquée pour représenter un objet que l'utilisateur puisse sélectionner.  Par exemple, vous pouvez utiliser le style d' `ILD_BLEND50` pour dessiner l'image lorsque l'utilisateur la sélectionne.  
  
 Une image non masquée est copiée dans le contexte de périphérique de destination à l'aide de l'opération de trame **SRCCOPY**.  Les couleurs dans l'image s'affichent de la même façon indépendamment de la couleur d'arrière\-plan du contexte de périphérique.  Les styles de dessin spécifiés dans **Dessiner** n'ont également aucun effet sur l'apparence d'une image non masquée.  
  
 En plus de la fonction membre Dessiner, une autre fonction, [DrawIndirect](../Topic/CImageList::DrawIndirect.md), étend la capacité d'afficher une image.  `DrawIndirect` prend comme paramètre une structure d' [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395).  Cette structure peut être utilisée pour personnaliser le rendu de l'image actuelle, notamment l'utilisation de codes d'opérations de trame \(ROP\).  Pour plus d'informations sur les codes d'opération de trame, consultez [Code d'opération de trame](http://msdn.microsoft.com/library/windows/desktop/dd162892) et [Bitmap comme pinceaux](http://msdn.microsoft.com/library/windows/desktop/dd183378) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Voir aussi  
 [Utilisation de CImageList](../mfc/using-cimagelist.md)   
 [Contrôles](../mfc/controls-mfc.md)