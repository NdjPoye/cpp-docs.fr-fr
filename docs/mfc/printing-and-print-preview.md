---
title: "Impression et Aperçu avant impression | Documents Microsoft"
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
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bedcf1ecf851ed6d9dd396ee6a82d6d2c058930b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="printing-and-print-preview"></a>Impression et aperçu avant impression
MFC prend en charge l’impression et Aperçu avant impression pour les documents de votre programme via la classe [CView](../mfc/reference/cview-class.md). Pour l’impression de base et Aperçu avant impression, simplement remplacer votre classe d’affichage [OnDraw](../mfc/reference/cview-class.md#ondraw) fonction membre, ce que vous devez faire quand même. Cette fonction peut dessiner dans la vue à l’écran, pour un contexte de périphérique pour une imprimante physique ou dans un contexte de périphérique qui simule votre imprimante à l’écran.  
  
 Vous pouvez également ajouter le code pour gérer l’impression du document multipage et aperçu, pour paginer vos documents imprimés et leur ajouter des en-têtes et pieds de page.  
  
 Cette famille d’articles explique comment l’impression est implémentée dans les MFC Microsoft Foundation Class Library () et comment tirer parti de l’architecture d’impression déjà intégrée à l’infrastructure. Ces articles expliquent également comment MFC prend en charge l’implémentation simple de la fonctionnalité d’aperçu avant impression, et comment vous pouvez utiliser et modifier cette fonctionnalité.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Que voulez-vous en savoir plus  
  
-   [Impression](../mfc/printing.md)  
  
-   [Architecture de l’aperçu avant impression](../mfc/print-preview-architecture.md)  
  
-   [Exemple](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Éléments d’Interface utilisateur](../mfc/user-interface-elements-mfc.md)
