---
title: "Impression | Microsoft Docs"
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
  - "documents, imprimer"
  - "imprimer (MFC)"
  - "imprimer (MFC), à partir de l'infrastructure"
  - "classes vues, opérations d'impression"
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Impression
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Windows implémente un affichage indépendant du périphérique.  Dans MFC, cela signifie que les mêmes appels de dessin, dans la fonction membre de `OnDraw` de la classe d'affichage, sont responsables de dessiner sur l'affichage et sur d'autres périphériques, tels que des imprimantes.  Pour l'aperçu avant impression, le périphérique cible est une sortie simulée d'imprimante vers l'affichage.  
  
##  <a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a> Le rôle de l'impression contre le rôle de l'infrastructure  
 Votre classe d'affichage a les responsabilités suivantes :  
  
-   Notifie à l'infrastructure le nombre de pages dans le document.  
  
-   Lorsque vous êtes invité à imprimer une page spécifiée, dessiner cette partie du document.  
  
-   Allouez et récupérez toutes les polices ou autres ressources de Graphics Device Interface\(GDI\) nécessaires pour l'impression.  
  
-   Si nécessaire, envoyez les codes d'échappement nécessaires pour modifier le mode d'imprimante avant impression d'une page spécifique, par exemple, pour modifier l'orientation d'impression pour chaque page.  
  
 Les responsabilités de l'infrastructure sont les suivantes :  
  
-   Afficher la boîte de dialogue **Imprimer**.  
  
-   Créez un objet de [CDC](../mfc/reference/cdc-class.md) pour l'imprimante.  
  
-   Appelez les fonctions membres de [StartDoc](../Topic/CDC::StartDoc.md) et de [EndDoc](../Topic/CDC::EndDoc.md) de l'objet de `CDC`.  
  
-   Appelez plusieurs fois la fonction membre de [DebutPage](../Topic/CDC::StartPage.md) de l'objet de `CDC`, la notification de la classe d'affichage ce que la page doit être imprimée, et appellent la fonction membre de [FinPage](../Topic/CDC::EndPage.md) de l'objet de `CDC`.  
  
-   Appelez les fonctions substituables à la vue aux moments appropriés.  
  
 Les éléments suivants décrivent comment l'infrastructure prend en charge l'impression et l'aperçu avant impression :  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Comment l'impression par défaut fonctionne](../mfc/how-default-printing-is-done.md)  
  
-   [Documents multipages](../mfc/multipage-documents.md)  
  
-   [En\-têtes et pieds de page](../mfc/headers-and-footers.md)  
  
-   [Allouer des ressources GDI pour l'impression](../mfc/allocating-gdi-resources.md)  
  
-   [Aperçu avant impression](../mfc/print-preview-architecture.md)  
  
## Voir aussi  
 [Impression et aperçu avant impression](../mfc/printing-and-print-preview.md)