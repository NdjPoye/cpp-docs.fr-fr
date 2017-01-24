---
title: "Dispositifs de suivi | Microsoft Docs"
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
  - "applications (OLE), dispositifs de suivi"
  - "CDC (classe), dispositifs de suivi"
  - "CRectTracker (classe), implémenter des dispositifs de suivi"
  - "OLE (applications) (C++), dispositifs de suivi"
  - "conteneurs OLE, dispositifs de suivi"
  - "applications serveur OLE, dispositifs de suivi"
  - "dispositifs de suivi"
  - "suivre des éléments OLE"
ms.assetid: dcd09399-6637-4621-80e5-d12670429787
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Dispositifs de suivi
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de [CRectTracker](../mfc/reference/crecttracker-class.md) fournit une interface utilisateur entre les éléments rectangulaires dans votre application et l'utilisateur en fournissant divers styles d'affichage.  Ces styles incluent les bordures pleines , hachées ou discontinues ; un modèle haché couvrant l'élément ; et poignées de redimensionnement qui peuvent être placées à l'extérieur ou à l'intérieur d'une bordure.  Les dispositifs de suivi sont souvent utilisés conjointement avec des éléments OLE, c. \- à\-d., les objets dérivés de `COleClientItem`.  Les rectangles de suivi donnent des signaux visuels sur l'état actuel de l'élément.  
  
 L'exemple de liaison et incorporation d'objets MFC [OCLIENT](../top/visual-cpp-samples.md) illustre une interface commune à des dispositifs de suivi et des éléments client OLE du point de vue d'une application conteneur.  Pour une démonstration des différents styles et capacités d'un dispositif de suivi objet, consultez l'exemple général MFC [DISPOSITIF DE SUIVI](../top/visual-cpp-samples.md).  
  
 Pour plus d'informations sur l'implémentation de l'unité de suivi dans votre application OLE, consultez [Dispositifs de suivi : Implémentation de l'unité de suivi dans votre application OLE](../mfc/trackers-implementing-trackers-in-your-ole-application.md)  
  
## Voir aussi  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleClientItem Class](../mfc/reference/coleclientitem-class.md)