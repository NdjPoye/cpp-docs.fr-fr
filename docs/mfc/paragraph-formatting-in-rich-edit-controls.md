---
title: "Mise en forme des paragraphes dans les contr&#244;les RichEdit | Microsoft Docs"
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
  - "CRichEditCtrl (classe), mise en forme des paragraphes"
  - "mise en forme (C++), paragraphes"
  - "mise en forme des paragraphes dans CRichEditCtrl"
  - "contrôles RichEdit, mise en forme des paragraphes"
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Mise en forme des paragraphes dans les contr&#244;les RichEdit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez les fonctions membres du contrôle RichEdit \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) pour mettre en forme les paragraphes et récupérer les informations de mise en forme.  Les attributs de format de paragraphe incluent l'inscription, les onglets, les retraits, et la numérotation.  
  
 Appliquez une mise en forme de paragraphe à l'aide de la fonction membre de [SetParaFormat](../Topic/CRichEditCtrl::SetParaFormat.md).  Pour déterminer la mise en forme de paragraphe actuelle du texte sélectionné, utilisez la fonction membre de [GetParaFormat](../Topic/CRichEditCtrl::GetParaFormat.md).  La structure de [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) est utilisée avec ces fonctions de membre pour spécifier des attributs de paragraphe.  L'un des membres importants de **PARAFORMAT** est **dwMask**.  Dans `SetParaFormat`, **dwMask** spécifie quels attributs de paragraphe sont définis par cet appel de fonction.  `GetParaFormat` indique les attributs du premier paragraphe de la sélection ; **dwMask** spécifie les attributs qui sont cohérents dans toute la sélection.  
  
## Voir aussi  
 [Utilisation de CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)