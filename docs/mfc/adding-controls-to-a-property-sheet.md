---
title: "Ajout de contrôles à une feuille de propriétés | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5623f95a77710e0ffbfa8a444de6f569f24105e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="adding-controls-to-a-property-sheet"></a>Ajout de contrôles à une feuille de propriétés
Par défaut, une feuille de propriétés alloue de la zone de fenêtre pour les pages de propriétés, l’index de tabulation et les boutons OK, Annuler et appliquer. (Une feuille de propriétés non modale n’a pas du OK, Annuler et appliquer des boutons.) Vous pouvez ajouter d’autres contrôles à la feuille de propriétés. Par exemple, vous pouvez ajouter une fenêtre d’aperçu à droite de la zone de page de propriétés pour afficher les paramètres actuels de l’aspect si appliqué à un objet externe.  
  
 Vous pouvez ajouter des contrôles à la boîte de dialogue de feuille de propriétés dans le `OnCreate` gestionnaire. Insertion de contrôles supplémentaires généralement requiert augmentant la taille de la boîte de dialogue de feuille de propriétés. Après l’appel de la classe de base **CPropertySheet::OnCreate**, appelez [GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect) pour obtenir la largeur et la hauteur de la fenêtre de feuille de propriétés, développez le rectangle dimensions et appel [MoveWindow](../mfc/reference/cwnd-class.md#movewindow) pour modifier la taille de la fenêtre de feuille de propriétés.  
  
## <a name="see-also"></a>Voir aussi  
 [Feuilles de propriétés](../mfc/property-sheets-mfc.md)   
 [CPropertyPage (classe)](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet, classe](../mfc/reference/cpropertysheet-class.md)
