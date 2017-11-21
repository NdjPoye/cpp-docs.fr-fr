---
title: "Contrôle de liste et vue liste | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListView class [MFC], and CListCtrl
- views [MFC], list and list control
- CListCtrl class [MFC], and CListView
- list views [MFC]
- list controls [MFC], List view
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 893ff83067c2a7fbc6c375dd6ee03248114ca5ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="list-control-and-list-view"></a>Contrôle de liste et vue Liste
Pour plus de commodité, MFC encapsule le contrôle de liste de deux manières. Vous pouvez utiliser les contrôles de liste :  
  
-   Directement, en incorporant un [CListCtrl](../mfc/reference/clistctrl-class.md) objet dans une classe de boîte de dialogue.  
  
-   Indirectement, à l’aide de classe [CListView](../mfc/reference/clistview-class.md).  
  
 `CListView`permet de facilement intégrer un contrôle de liste avec l’architecture document/vue MFC, en encapsulant le contrôle une grande partie comme [CEditView](../mfc/reference/ceditview-class.md) encapsule un contrôle d’édition : le contrôle remplit toute la surface d’une vue MFC. (La vue *est* le contrôle, casté en `CListView`.)  
  
 A `CListView` hérite de l’objet [CCtrlView](../mfc/reference/cctrlview-class.md) et classes de base et ajoute une fonction membre pour récupérer le contrôle de liste sous-jacente. Afficher les membres permet de travailler avec la vue comme une vue. Utilisez le [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl) fonction membre pour accéder aux fonctions membres du contrôle de liste. Utilisez ces membres :  
  
-   Ajouter, supprimer ou manipuler les « éléments » dans la liste.  
  
-   Définir ou obtenir des attributs de contrôle de liste.  
  
 Pour obtenir une référence à la `CListCtrl` sous-jacent un `CListView`, appelez `GetListCtrl` à partir de votre classe d’affichage de liste :  
  
 [!code-cpp[NVC_MFCListView#4](../atl/reference/codesnippet/cpp/list-control-and-list-view_1.cpp)]  
  
 Cette rubrique décrit deux façons d’utiliser le contrôle de liste.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

