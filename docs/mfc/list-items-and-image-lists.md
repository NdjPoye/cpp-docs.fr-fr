---
title: "&#201;l&#233;ments de liste et listes d&#39;images | Microsoft Docs"
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
  - "CImageList (classe), et éléments de liste"
  - "CListCtrl (classe), listes d'images"
  - "listes d'images (C++), éléments de liste"
  - "éléments de liste, listes d'images"
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;l&#233;ments de liste et listes d&#39;images
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un « élément » dans un contrôle de liste \([CListCtrl](../mfc/reference/clistctrl-class.md)\) est constitué d'une icône, d'un nom, et éventuellement d'autres informations \(dans la section « sous\-éléments »\).  
  
 Les icônes des éléments de liste de contrôle figurent dans les listes des images.  Une liste d'images contient des icônes de taille normale utilisées dans la vue de l'icône.  Une deuxième liste d'images, facultative, contient de plus petites versions des mêmes icônes pour une utilisation dans d'autres vues du contrôle.  Une troisième liste facultative contient des images « état », telles que des listes de cases à cocher, pour l'affichage devant les petites icônes dans certaines vues.  Une quatrième liste facultative contient les images affichées dans des éléments d'en\-tête individueal du contrôle de liste.  
  
> [!NOTE]
>  Si une commande d'affichage de liste est créée avec le style d' `LVS_SHAREIMAGELISTS`, vous êtes chargé de détruire les listes d'images lorsqu'elles ne sont plus utilisées.  Spécifiez ce style si vous attribuez les mêmes listes d'images à plusieurs vérifications d'affichage de vue; sinon, plus d'un contrôle peut essayer de détruire la même liste d'images.  
  
 Pour plus d'informations sur les éléments de liste, consultez [Listes images d'affichage de listes](http://msdn.microsoft.com/library/windows/desktop/bb774736) [Éléments et sous\-éléments](http://msdn.microsoft.com/library/windows/desktop/bb774736) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Consultez également la classe [CImageList](../mfc/reference/cimagelist-class.md) dans le *guide de référence MFC* et l' [Utilisation CImageList](../mfc/using-cimagelist.md) dans la famille des articles.  
  
 Pour créer un contrôle de liste, vous devez fournir des listes d'images à utiliser lorsque vous insérez des éléments dans la liste.  L'exemple suivant illustre cette procédure, où `m_pImagelist` est un pointeur de type `CImageList` et `m_listctrl` est un membre de données de `CListCtrl`.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/CPP/list-items-and-image-lists_1.cpp)]  
  
 Toutefois, si vous n'envisagez pas d'afficher les icônes dans l'affichage de liste ou le contrôle de liste, vous n'avez pas besoin de listes d'image.  
  
## Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)