---
title: "Glisser-d&#233;placer (OLE) | Microsoft Docs"
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
  - "glisser-déplacer (C++)"
  - "glisser-déplacer (C++), à propos du glisser-déplacer OLE"
  - "Gestionnaire de fichiers (glisser-déplacer) (prise en charge)"
  - "applications OLE, glisser-déplacer"
  - "OLE (glisser-déplacer)"
  - "applications serveur OLE, glisser-déplacer"
ms.assetid: a4595350-ca06-4400-88a1-f0175c76b77b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Glisser-d&#233;placer (OLE)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La fonctionnalité glisser\-déplacer de l'OLE est essentiellement un raccourci pour copier et coller des données.  Lorsque vous utilisez le presse\-papiers pour copier et coller des données, un certain nombre d'étapes sont nécessaires.  Vous sélectionnez les données, cliquez sur **Couper** ou **Copier** dans le menu de **Modifier**, de déplacer le fichier de destination, d'affichage ou de l'application, placez le curseur dans l'emplacement souhaité, puis cliquez sur **Coller** dans le menu de **Modifier**.  
  
 Le glisser\-déplacer de l'OLE est différent du mécanisme glissé\-déplacé du gestionnaire de fichiers, qui ne peut gérer que les noms de fichiers et est conçu spécifiquement pour passer les noms de fichiers pour les applications.  Le glisser\-déplacer de l'OLE est beaucoup plus général.  Vous pouvez ainsi faire glisser toutes les données qui peuvent être placées dans le presse\-papiers.  
  
 Lorsque vous utilisez le glisser\-déplacer OLE, vous supprimez deux étapes du processus.  Vous sélectionnez les données de la fenêtre source \(la source « drop »\), la faites glisser vers la destination souhaitée \(la cible de « drop »\), puis la supprimez en libérant le bouton de la souris.  L'opération élimine le besoin de menus et est plus rapide que la copie\/séquence de collage.  Le seul impératif est que la source de déplacement et la cible de suppression doivent être ouverts et au moins partiellement visibles à l'écran.  
  
 À l'aide d'une glisser\-déplacer OLE, les données peuvent être transférées d'un emplacement à un autre dans un document, entre des documents, ou entre des applications.  Il peut être implémenté dans un conteneur ou une application serveur, et toute application peut être une source déroulante, une cible de suppression, ou les deux.  Si une application a la source de déplacement et la prise en charge de suppression de cible implémentées, le glisser\-déplacer est activé entre les fenêtres enfants, ou dans une fenêtre.  Cette fonctionnalité permet de rendre votre application plus facile à utiliser.  
  
 Si vous souhaitez simplement utiliser les fonctions glissées\-déplacées OLE, consultez le [Faites glisser : Personnalisation](../mfc/drag-and-drop-customizing.md).  Vous pouvez utiliser les techniques expliquées dans cet article pour effectuer des sources de suppression des applications de type OLE.  L'article [Faites glisser : Implémenter une cible de suppression](../mfc/drag-and-drop-implementing-a-drop-target.md) explique comment implémenter la prise en charge de suppression de cible applications de OLE et non OLE.  Il est également utile d'examiner les exemples de liaison et incorporation d'objets MFC [OCLIENT](../top/visual-cpp-samples.md) et [HIERSVR](../top/visual-cpp-samples.md).  
  
 Si vous n'avez pas lu la famille de [Objets de données et sources de données \(OLE\)](../mfc/data-objects-and-data-sources-ole.md) des articles, vous pouvez le faire maintenant.  Ces articles expliquent les aspects fondamentaux de transfert de données, ainsi que l'implémentation dans vos applications.  
  
 Pour plus d'informations sur le glisser\-déplacer, consultez :  
  
-   [Glisser\-déplacer : implémentation d'une source de déplacement](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [Glisser\-déplacer : implémentation d'une cible de déplacement](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [Glisser\-déplacer : personnalisation](../mfc/drag-and-drop-customizing.md)  
  
## Voir aussi  
 [OLE](../mfc/ole-in-mfc.md)   
 [Objets de données et sources de données \(OLE\)](../mfc/data-objects-and-data-sources-ole.md)