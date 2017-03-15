---
title: "Utilisation d&#39;un contr&#244;le Animation | Microsoft Docs"
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
  - "contrôles animation (C++)"
  - "CAnimateCtrl (classe), contrôles animation"
  - "contrôles (MFC), animation"
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation d&#39;un contr&#244;le Animation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'utilisation standard d'un contrôle d'animations suit le modèle ci\-dessous :  
  
-   Le contrôle est créé.  Si le contrôle est spécifié dans un modèle de la boîte de dialogue, la création est automatique lorsque la boîte de dialogue est créée. \(Vous devez être membre de [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) dans la classe de la boîte de dialogue correspondant au contrôle d'animations.\) Ou bien, vous pouvez utiliser la fonction membre de [Créer](../Topic/CAnimateCtrl::Create.md) pour créer le contrôle dans une fenêtre enfant de toute fenêtre.  
  
-   Charger un AVI clip dans le contrôle animations en appelant la fonction membre de [Ouvrir](../Topic/CAnimateCtrl::Open.md).  Si votre contrôle animations est dans une boîte de dialogue, beaucoup de place pour cela est dans la fonction de [SurDialogueInitial](../Topic/CDialog::OnInitDialog.md) de la classe de dialogue.  
  
-   Lancez le clip en appelant la fonction membre de [Lecture](../Topic/CAnimateCtrl::Play.md).  Si votre contrôle animations est dans une boîte de dialogue, beaucoup de place pour cela est dans la fonction de **SurDialogueInitial** de la classe de dialogue.  Appeler **Lecture** n'est pas nécessaire si le contrôle animations a le style de `ACS_AUTOPLAY` défini.  
  
-   Si vous souhaitez afficher des parties du clip ou de le jouer cadre par cadre, utilisez la fonction membre de `Seek`.  Pour arrêter un clip qui joue, utilisez la fonction membre de `Stop`.  
  
-   Si vous n'allez pas détruire le contrôle immédiatement, supprimez le clip de la mémoire en appelant la fonction membre du **Fermer**.  
  
-   Si le contrôle animations est dans une boîte de dialogue, lui et l'objet de `CAnimateCtrl` sont détruits automatiquement.  Sinon, vous devez vérifier que le flux de contrôle et l'objet de `CAnimateCtrl` sont correctement détruits.  La destruction du contrôle ferme automatiquement le AVI clip.  
  
## Voir aussi  
 [Utilisation de CAnimateCtrl](../mfc/using-canimatectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)