---
title: "En-t&#234;tes et pieds de page | Microsoft Docs"
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
  - "pieds de page, imprimer"
  - "en-têtes, imprimer"
  - "pieds de page"
  - "pieds de page, imprimer"
  - "en-têtes de page"
  - "en-têtes de page, imprimer"
  - "imprimer (MFC), en-têtes et pieds de page"
  - "imprimer (MFC), documents multipages"
ms.assetid: b0be9c53-5773-4955-a777-3c15da745128
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# En-t&#234;tes et pieds de page
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment ajouter des en\-têtes et pieds de page à un document imprimé.  
  
 Lorsque vous regarder un document à l'écran, le nom du document et la position actuelle dans le document sont généralement affichés dans la barre de titre et la barre d'état.  En consultant une copie imprimée d'un document, il est utile d'avoir le nom et le numéro de page affichés dans un en\-tête ou un pied de page.  C'est un point fréquent sur lequel même les programmes de WYSIWYG diffèrent dans la façon dont ils effectuent l'impression et l'affichage à l'écran.  
  
 La fonction membre [OnPrint](../Topic/CView::OnPrint.md) est l'emplacement approprié pour imprimer les en\-têtes ou pieds de page car elle est appelée pour chaque page, et elle est appelée uniquement pour l'impression, et non pour l'affichage à l'écran.  Vous pouvez définir une fonction distincte pour imprimer un en\-tête ou un pied de page, et lui passer le contexte de l'imprimante `OnPrint`.  Vous devrez peut\-être ajuster l'origine ou l'étendue de la fenêtre avant d'appeler [OnDraw](../Topic/CView::OnDraw.md) pour éviter le chevauchement du corps de la page et de l'en\-tête ou du pied de page.  Vous devrez peut\-être modifier `OnDraw` car la quantité de document qui tient dans la page peut être réduite.  
  
 Une façon de compenser la zone prise par l'en\-tête ou le pied de page est d'utiliser le membre de **m\_rectDraw** de [CPrintInfo](../mfc/reference/cprintinfo-structure.md).  Chaque fois qu'une page est imprimée, ce membre est initialisé avec la zone utilisable de la page.  Si vous imprimez un en\-tête ou un pied de page avant impression du corps de la page, vous pouvez réduire la taille du rectangle stocké dans **m\_rectDraw** pour représenter la zone prise par l'en\-tête ou le pied de page.  Alors`OnPrint` peut se référer à **m\_rectDraw** pour déterminer la zone qui reste pour imprimer le corps de la page.  
  
 Vous ne pouvez pas afficher un en\-tête, ou quoi que ce soit d'autre, à partir de [OnPrepareDC](../Topic/CView::OnPrepareDC.md), car elle est appelée avant que la fonction membre `StartPage` de [CDC](../mfc/reference/cdc-class.md) a été appelée.  À ce stade, le contexte de l'imprimante est considéré comme à la bordure d'une page.  Vous pouvez exécuter l'impression seulement depuis la fonction membre `OnPrint`.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [imprimer des documents multipages](../mfc/multipage-documents.md)  
  
-   [Allouer des ressources GDI pour l'impression](../mfc/allocating-gdi-resources.md)  
  
## Voir aussi  
 [Impression](../mfc/printing.md)