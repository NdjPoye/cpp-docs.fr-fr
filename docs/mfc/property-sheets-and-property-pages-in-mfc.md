---
title: "Pages et feuilles de propri&#233;t&#233;s dans MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles (MFC), feuilles de propriétés"
  - "pages de propriétés, MFC"
  - "feuilles de propriétés, MFC"
  - "boîtes de dialogue avec onglets"
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Pages et feuilles de propri&#233;t&#233;s dans MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une feuille de propriétés, également appelée boîte de dialogue de l'onglet, est une boîte de dialogue contenant des pages de propriétés.  Chaque page de propriétés est basée sur une ressource modèle de la boîte de dialogue et contient des contrôles.  Elle est placée dans une page possédant un onglet en haut.  L'onglet nomme la page et indique sa fonction.  Les utilisateurs cliquent sur un onglet de la feuille de propriétés afin de sélectionner un ensemble de contrôles.  
  
 Utilisez les pages pour regrouper les contrôles de la feuille de propriétés dans des ensembles sensés.  La feuille de propriétés contenue contient elle\-même généralement plusieurs commandes.  Cela s'applique à toutes les pages.  
  
 Les feuilles de propriétés sont basés sur la classe [CPropertySheet](../mfc/reference/cpropertysheet-class.md).  Les pages de propriétés sont basés sur la classe [CPropertyPage](../mfc/reference/cpropertypage-class.md).  
  
 Une feuille de propriétés est un type spécial de boîte de dialogue utilisé en général pour modifier les attributs de certains objets externes, tels que la sélection actuelle dans un affichage.  La feuille de propriétés comporte trois parties principales : la boîte de dialogue conteneur, une ou plusieurs pages de propriétés affichées une par une, ainsi qu'un onglet situé en haut de chaque page sur laquelle l'utilisateur clique pour sélectionner cette page.  Les feuilles de propriétés sont utiles pour des situations où vous avez plusieurs groupes similaires de paramètres ou d'options à modifier.  Une feuille de propriétés regroupe les informations de manière facilement compréhensible.  
  
> [!NOTE]
>  Lorsque vous essayez d'afficher une feuille de propriétés à l'aide de `CPropertySheet::DoModal`, le système peut générer une exception de premier essai.  Cette erreur se produit parce que le système tente de modifier le [Styles de fenêtre](../mfc/reference/window-styles.md) de l'objet avant que l'objet ait été créé.  Pour plus d'informations sur cette exception, et également comment l'éviter ou la gérer, consultez [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md).  
  
## Voir aussi  
 [Feuilles de propriétés](../mfc/property-sheets-mfc.md)