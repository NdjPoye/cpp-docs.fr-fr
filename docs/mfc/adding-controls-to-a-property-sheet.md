---
title: "Ajout de contr&#244;les &#224; une feuille de propri&#233;t&#233;s | Microsoft Docs"
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
  - "contrôles (MFC), ajouter aux feuilles de propriétés"
  - "feuilles de propriétés, ajouter des contrôles"
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout de contr&#244;les &#224; une feuille de propri&#233;t&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Par défaut, une feuille de propriétés alloue une zone de la fenêtre pour les pages de propriétés, l'index de l'onglet et pour les bouton OK, Annuler et Appliquer. \(Une feuille de propriétés non modales n'a pas les boutons OK, Annuler et Appliquer.\) Vous pouvez ajouter d'autres contrôles à la feuille de propriétés.  Par exemple, vous pouvez ajouter une fenêtre d'aperçu à droite de la zone de la page des propriétés pour indiquer à l'utilisateur à quoi ressembleraient les paramètres actuels s'ils étaient appliqués à un objet externe.  
  
 Vous pouvez ajouter des contrôles au dialogue de la feuille de propriétés dans le gestionnaire de `OnCreate`.  Accommoder des contrôles supplémentaires requiert généralement augmenter la taille de la feuille de propriétés du dialogue.  Après avoir appelé la classe de base **CPropertySheet::OnCreate**, appelez [GetWindowRect](../Topic/CWnd::GetWindowRect.md) pour obtenir la largeur et la hauteur de la fenêtre de propriétés actuellement allouée, augmentez les dimensions du rectangle, puis appelez [MoveWindow](../Topic/CWnd::MoveWindow.md) pour modifier la taille de la fenêtre de la feuille de propriétés.  
  
## Voir aussi  
 [Feuilles de propriétés](../mfc/property-sheets-mfc.md)   
 [CPropertyPage Class](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet Class](../mfc/reference/cpropertysheet-class.md)