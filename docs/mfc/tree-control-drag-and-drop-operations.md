---
title: "Op&#233;rations de glisser-d&#233;placer pour le contr&#244;le d&#39;arborescence | Microsoft Docs"
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
  - "CTreeCtrl (classe), opérations de glisser-déplacer"
  - "glisser-déplacer, CTreeCtrl"
  - "contrôles d'arborescence, opérations de glisser-déplacer"
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rations de glisser-d&#233;placer pour le contr&#244;le d&#39;arborescence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un contrôle d'arborescence \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) envoie une notification quand l'utilisateur commence à faire glisser un élément.  Le contrôle envoie un message de notification [TVN\_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773504) lorsque l'utilisateur commence à faire glisser un élément avec le bouton gauche de la souris et un message de notification [TVN\_BEGINRDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773509) lorsque l'utilisateur commence à faire glisser un élément en cliquant sur le bouton droit.  Vous pouvez empêcher un contrôle d'arborescence d'envoyer des notifications en donnant au contrôle d'arborescence le style **TVS\_DISABLEDRAGDROP**.  
  
 Vous obtenez une image à afficher lors d'une opération glisser\-déplacer en appelant la méthode [CreateDragImage](../Topic/CTreeCtrl::CreateDragImage.md).  L'arborescence crée une bitmap de glissement basée sur le nom de l'élément déplacé.  Le contrôle d'aborescence crée une liste des images, y ajoute une bitmap, et retourne un pointeur vers l'objet [CImageList](../mfc/reference/cimagelist-class.md).  
  
 Vous devez fournir du code faisant glisser réellement l'élément.  Cela se fait généralement en utilisant les fonctions de déplacement de la liste des images et le traitement des messages [WM\_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) et [WM\_LBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms645608) \(ou [WM\_RBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646243)\) envoyés après le début de l'opération de déplacement.  Pour plus d'informations sur les fonctions de liste des images, consultez [CImageList](../mfc/reference/cimagelist-class.md) dans *le guide de MFC* et [Listes des images](http://msdn.microsoft.com/library/windows/desktop/bb761389) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Pour plus d'informations sur le déplacement d'un élément de l'arborescence, consultez [Déplacer l'élément d'arborescence](http://msdn.microsoft.com/library/windows/desktop/bb760017), également dans [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  
  
 Si les éléments d'un contrôle d'arborescence vont être des cibles d'opérations de glisser\-déplacer, vous devez savoir quand le curseur de la souris est sur un élément cible.  Vous pouvez déterminer en appelant la méthode [HitTest](../Topic/CTreeCtrl::HitTest.md).  Vous spécifiez un point et un entier, ou l'adresse d'une structure [TVHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb773448) qui contient les coordonnées actuelles du curseur de la souris.  Lorsque la fonction retourne, l'entier ou la structure contient un indicateur qui indique l'emplacement du curseur de la souris par rapport au contrôle d'arborescence.  Si le curseur est sur un élément dans l'arborescence, la structure contient également le handle de l'élément.  
  
 Vous pouvez indiquer qu'un élément est la cible d'une opération de glisser\-déplacer en appelant la méthode [SetItem](../Topic/CTreeCtrl::SetItem.md) pour définir le statut à la valeur `TVIS_DROPHILITED`.  Un élément qui possède cet état est tracé dans le style utilisé pour indiquer une cible par glisser\-déplacer.  
  
## Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)