---
title: "Feuilles de propriétés sous forme d’Assistants | Documents Microsoft"
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
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 65aedc5dbeb8a740d5713983f66eefe693864937
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="property-sheets-as-wizards"></a>Feuilles de propriétés sous forme d'assistants
Une caractéristique clé d’une feuille de propriétés Assistant est que la navigation est fournie avec les boutons suivant ou terminer, précédent et annuler au lieu d’onglets. Vous devez appeler [fonction CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) avant d’appeler [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal) sur l’objet de feuille de propriétés pour tirer parti de cette fonctionnalité.  
  
 L’utilisateur reçoit le même [notifications CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) et [CPropertyPage::OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) notifications lors du déplacement d’une page vers une autre page. Boutons suivant et terminer excluent mutuellement ; Autrement dit, un seul d'entre eux s’affichera à la fois. Sur la première page, le bouton suivant doit être activé. Si l’utilisateur est dans la dernière page, le bouton Terminer doit être activé. Pas cela automatiquement par l’infrastructure. Vous devez appeler [fonction CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) sur la dernière page à effectuer cette opération.  
  
 Pour afficher tous les boutons par défaut, vous devez afficher le bouton Terminer et déplacer le bouton suivant. Puis déplacez le bouton précédent afin que sa position relative pour le bouton suivant est maintenue.  
  
## <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Feuilles de propriétés](../mfc/property-sheets-mfc.md)

