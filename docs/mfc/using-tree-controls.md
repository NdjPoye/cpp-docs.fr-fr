---
title: "Utilisation de contr&#244;les d&#39;arborescence | Microsoft Docs"
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
  - "CTreeCtrl (classe), utilisation"
  - "contrôles d'arborescence, à propos des contrôles d'arborescence"
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de contr&#244;les d&#39;arborescence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'utilisation standard d'un contrôle d'arbre \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) suit le modèle ci\-dessous :  
  
-   Le contrôle est créé.  Si le contrôle est spécifié dans un modèle de boîte de dialogue ou si vous utilisez `CTreeView`, la création est automatique lorsque la boîte de dialogue ou la vue est créée.  Si vous souhaitez créer l'arbre dans une fenêtre enfant d'une autre fenêtre, utilisez la méthode [Créer](../Topic/CTreeCtrl::Create.md).  
  
-   Si vous souhaitez que votre contrôle d'arbre utilise des images, générez liste des images en appelant [SetImageList](../Topic/CTreeCtrl::SetImageList.md).  Vous pouvez également modifier l'indentation en appelant [SetIndent](../Topic/CTreeCtrl::SetIndent.md).  Un bon moment pour cela est dans [OnInitDialog](../Topic/CDialog::OnInitDialog.md) \(pour les contrôles dans les boîtes de dialogue\) ou [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) \(pour les vues\).  
  
-   Placez les données dans le contrôle en appelant la fonction[InsertItem](../Topic/CTreeCtrl::InsertItem.md) de `CTreeCtrl` une fois pour chaque élément de données.  `InsertItem` retourne un handle de l'élément que vous pouvez utiliser pour y faire référence ultérieurement, par exemple en ajoutant des éléments enfants.  Un bon moment pour initialiser les données est dans `OnInitDialog` \(pour les contrôles dans les boîtes de dialogue\) ou `OnInitialUpdate` \(pour les vues\).  
  
-   Lorsque l'utilisateur interagit avec le contrôle, il envoie des messages de notification.  Vous pouvez spécifier une fonction pour gérer les messages à traiter en ajoutant une macro **ON\_NOTIFY\_REFLECT** dans la table des messages de la fenêtre de contrôle ou en ajoutant une macro`ON_NOTIFY` à la table des messages de la fenêtre parent.  Voir [Messages de notification d'arbre](../mfc/tree-control-notification-messages.md) plus loin dans cette rubrique pour obtenir la liste des notifications possibles.  
  
-   Appelez plusieurs fonctions membres Set pour définir les valeurs du contrôle.  Les modifications que vous pouvez faire inclusent définir la mise en retrait et la modification du texte, des images, ou des données associées à un élément.  
  
-   Utilisez les différentes fonctions Get pour examiner le contenu du contrôle.  Vous pouvez également parcourir le contenu du contrôle d'arbre avec des fonctions qui vous permettent de récupérer les handles vers les parents, les enfants, et les frères d'un élément spécifié.  Vous pouvez même trier les enfants d'un nœud particulier.  
  
-   Lorsque vous en avez terminé avec le contrôle, assurez vous qu'il est correctement détruit.  Si le contrôle d'arbre est dans une boîte de dialogue ou s'il s'agit d'une vue, lui et l'objet `CTreeCtrl` sont détruits automatiquement.  Sinon, vous devez vérifier que le contrôle et l'objet `CTreeCtrl` sont correctement détruits.  
  
## Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)