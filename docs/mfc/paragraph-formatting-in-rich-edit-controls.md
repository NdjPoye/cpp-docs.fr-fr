---
title: "Mise en forme dans les contrôles RichEdit | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0f0dc12d923f6f424fe84768b0d934d8dd7ff20b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Mise en forme des paragraphes dans les contrôles RichEdit
Vous pouvez utiliser les fonctions membres du contrôle RichEdit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) pour mettre en forme les paragraphes et pour récupérer les informations de mise en forme. Attributs de mise en forme de paragraphe incluent l’alignement, les onglets, les retraits et la numérotation.  
  
 Vous pouvez appliquer la mise en forme à l’aide de la [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) fonction membre. Pour déterminer la mise en forme pour le texte sélectionné, utilisez le [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) fonction membre. Le [RAJOUTER](http://msdn.microsoft.com/library/windows/desktop/bb787940) structure est utilisée avec ces fonctions membres pour spécifier des attributs de paragraphe. Un des membres importants de **RAJOUTER** est **dwMask**. Dans `SetParaFormat`, **dwMask** spécifie les attributs de paragraphe seront définis par cet appel de fonction. `GetParaFormat`Indique les attributs du premier paragraphe de la sélection ; **dwMask** spécifie les attributs qui sont cohérentes dans la sélection.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

