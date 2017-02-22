---
title: "Feuilles de propri&#233;t&#233;s sous forme d&#39;assistants | Microsoft Docs"
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
  - "feuilles de propriétés, sous forme d'assistants"
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Feuilles de propri&#233;t&#233;s sous forme d&#39;assistants
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une caractéristique clé d'une feuille de propriétés daAssistant est que la navigation est fournie avec les boutons Suivant ou Terminer, Retour, et Annuler au lieu des onglets.  Vous devez appeler [CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md) avant d'appeler [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md) sur l'objet de feuille de propriétés pour tirer parti de cette fonctionnalité.  
  
 L'utilisateur reçoit les mêmes notifications [CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md) et [CPropertyPage::OnKillActive](../Topic/CPropertyPage::OnKillActive.md) lors du déplacement d'une page vers une autre page.  Les boutons Suivant et Terminer sont des contrôles mutuellement exclusifs ; autrement dit, seule l'un d'eux est montré à la fois.  Dans la première page, le bouton suivant doit être activé.  Si l'utilisateur est sur la dernière page, le bouton terminer doit être activé.  Cela n'est pas fait automatiquement par le framework.  Vous devez appeler [CPropertySheet::SetWizardButton](../Topic/CPropertySheet::SetWizardButtons.md) sur la dernière page pour ce faire.  
  
 Pour afficher tous les boutons par défaut, vous devez montrer le bouton terminer et déplacer le bouton suivant.  Déplacez le bouton précédent afin que sa position relative par rapport au bouton suivant soit conservée.  Pour de plus d'explications, recherchez l'article de la Base de connaissances Q143210.  Vous pouvez rechercher des articles sur la Base de connaissances dans MSDN library.  
  
## Exemple  
 [!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/CPP/property-sheets-as-wizards_1.cpp)]  
  
## Voir aussi  
 [Feuilles de propriétés](../mfc/property-sheets-mfc.md)