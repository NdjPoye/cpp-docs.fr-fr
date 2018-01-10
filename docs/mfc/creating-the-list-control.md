---
title: "Création du contrôle de liste | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 85afbe49943e06a66cf2fa914cc87f07b0fa8c52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-list-control"></a>Création du contrôle de liste
Comment le contrôle de liste ([CListCtrl](../mfc/reference/clistctrl-class.md)) est créé varie selon que vous soyez l’utilisation du contrôle directement ou à l’aide de la classe [CListView](../mfc/reference/clistview-class.md) à la place. Si vous utilisez `CListView`, l’infrastructure construit l’affichage dans le cadre de sa séquence de création de document/vue. Création de l’affichage de liste crée également le contrôle de liste (les deux sont identiques). Le contrôle est créé dans la vue [OnCreate](../mfc/reference/cwnd-class.md#oncreate) fonction gestionnaire. Dans ce cas, le contrôle est prêt à ajouter des éléments, via un appel à [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl).  
  
### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>Pour utiliser CListCtrl directement dans une boîte de dialogue  
  
1.  Dans l’éditeur de boîte de dialogue, ajoutez un contrôle de liste à votre ressource de modèle de boîte de dialogue. Spécifier son ID de contrôle.  
  
2.  Utilisez le [Assistant Ajout de Variable membre](../ide/adding-a-member-variable-visual-cpp.md) pour ajouter une variable membre de type `CListCtrl` avec la propriété du contrôle. Vous pouvez utiliser ce membre pour appeler `CListCtrl` fonctions membres.  
  
3.  Utilisez la fenêtre Propriétés pour mapper des fonctions de gestionnaire de la classe de boîte de dialogue pour les messages de notification du contrôle list vous devez gérer (consultez [mappage de Messages à des fonctions](../mfc/reference/mapping-messages-to-functions.md)).  
  
4.  Dans [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), définissez les styles pour le `CListCtrl`. Consultez [modification des Styles de contrôle de liste](../mfc/changing-list-control-styles.md). Ce paramètre détermine le type de « vue », que vous obtenez dans le contrôle, bien que vous pouvez modifier ultérieurement la vue.  
  
### <a name="to-use-clistctrl-in-a-nondialog-window"></a>Pour utiliser CListCtrl dans un autre type de fenêtre  
  
1.  Définissez le contrôle dans la classe d’affichage ou de la fenêtre.  
  
2.  Appel du contrôle [créer](../mfc/reference/clistctrl-class.md#create) fonction membre, éventuellement dans [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), éventuellement en même temps que la fenêtre parente [OnCreate](../mfc/reference/cwnd-class.md#oncreate) fonction de gestionnaire (si vous êtes le sous-classement du contrôle). Définissez les styles pour le contrôle.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

