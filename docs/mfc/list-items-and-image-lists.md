---
title: "Éléments de liste et listes d’images | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 525d8353c308796d70f974fa56cde3aa76c12142
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="list-items-and-image-lists"></a>Éléments de liste et listes d'images
Un « élément » dans un contrôle de liste ([CListCtrl](../mfc/reference/clistctrl-class.md)) se compose d’une icône, une étiquette et éventuellement d’autres informations (en « sous-éléments »).  
  
 Les icônes des éléments de liste de contrôle sont contenus dans les listes d’images. Une liste d’images contient les icônes de taille réelle utilisées en mode icône. Une liste d’images deuxième, facultatif, contient des versions plus petites icônes même pour une utilisation dans d’autres affichages du contrôle. Une troisième liste, facultative contient les images de « état », tels que les cases à cocher, pour l’affichage devant les petites icônes dans certains modes d’affichage. Une quatrième liste, facultative contient les images qui sont affichées dans les éléments d’en-tête individuels du contrôle de liste.  
  
> [!NOTE]
>  Si un contrôle list view est créé avec le `LVS_SHAREIMAGELISTS` style, vous êtes responsable de la destruction des listes d’images lorsqu’ils ne sont plus en cours d’utilisation. Spécifiez ce style si vous attribuez la même image répertorie plusieurs contrôles d’affichage de liste ; dans le cas contraire, plusieurs contrôles peuvent essayer de détruire la même liste d’images.  
  
 Pour plus d’informations sur les éléments de liste, consultez [List View Image Lists](http://msdn.microsoft.com/library/windows/desktop/bb774736) et [éléments et sous-éléments](http://msdn.microsoft.com/library/windows/desktop/bb774736) dans le Kit de développement logiciel Windows. Consultez également la classe [CImageList](../mfc/reference/cimagelist-class.md) dans les *référence MFC* et [utilisation de CImageList](../mfc/using-cimagelist.md) dans cette famille d’articles.  
  
 Pour créer un contrôle de liste, vous devez fournir des listes d’images à utiliser lorsque vous insérez des nouveaux éléments dans la liste. L’exemple suivant illustre cette procédure, où `m_pImagelist` est un pointeur de type `CImageList` et `m_listctrl` est un `CListCtrl` membre de données.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/cpp/list-items-and-image-lists_1.cpp)]  
  
 Toutefois, si vous ne prévoyez pas d’afficher des icônes dans votre affichage de liste ou d’un contrôle de liste, vous n’avez pas besoin listes d’images.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

