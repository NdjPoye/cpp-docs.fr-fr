---
title: "Glisser-d&#233;placer&#160;: impl&#233;mentation d&#39;une source de d&#233;placement | Microsoft Docs"
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
  - "glisser-déplacer, appeler DoDragDrop"
  - "glisser-déplacer, source de déplacement"
  - "glisser-déplacer, lancer des opérations de glissement"
  - "OLE (glisser-déplacer), appeler DoDragDrop"
  - "OLE (glisser-déplacer), source de déplacement"
  - "OLE (glisser-déplacer), lancer des opérations de glissement"
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Glisser-d&#233;placer&#160;: impl&#233;mentation d&#39;une source de d&#233;placement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment faire en sorte que votre application fournisse des données à une opération de glisser\-déplacer.  
  
 L'implémentation de base d'une source de suppression est relativement simple.  La première étape consiste à déterminer quels événements démarrent une une opération de glisser\-déplacer.  Les instructions recommandées d'interface utilisateur définissent le démarrage d'une opération de glisse comme la sélection des données et un événement `WM_LBUTTONDOWN` survenant sur un point au sein des données sélectionnées.  Les exemples MFC OLE [OCLIENT](../top/visual-cpp-samples.md) et [HIERSVR](../top/visual-cpp-samples.md) respectent les principes suivants.  
  
 Si votre application est un conteneur et les données sélectionnées sont un objet lié ou incorporé de type `COleClientItem`, appelez la fonction membre `DoDragDrop`.  Sinon, construisez un objet `COleDataSource`, initialisez\-le à la sélection, puis appelez la fonction membre `DoDragDrop` de l'objet source de données.  Si votre application est un serveur, utilisez `COleServerItem::DoDragDrop`.  Pour plus d'informations sur la personnalisation de comportement standard de glissé\-déplacé, consultez l'article [Faites glisser : Personnalisation](../mfc/drag-and-drop-customizing.md).  
  
 Si `DoDragDrop` retourne `DROPEFFECT_MOVE`, supprimez immédiatement les données sources du document source.  Aucune autre valeur de retour de `DoDragDrop` n'a d'effet sur une source de suppression.  
  
 Pour plus d'informations, consultez :  
  
-   [Implémenter des cibles de déplacement](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [Personnalisation de Glisser\-déplacer](../mfc/drag-and-drop-customizing.md)  
  
-   [Création et Destruction d'Objets de données et de sources de données OLE](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Manipuler des Objets de données et Sources de données OLE](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## Voir aussi  
 [Glisser\-déplacer \(OLE\)](../mfc/drag-and-drop-ole.md)   
 [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)   
 [COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md)   
 [CView::OnDragLeave](../Topic/CView::OnDragLeave.md)