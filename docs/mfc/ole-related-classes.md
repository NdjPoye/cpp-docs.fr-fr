---
title: "Classes li&#233;es &#224; OLE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes ActiveX (C++)"
  - "OLE (C++), classes"
  - "OLE (classes) (C++)"
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes li&#233;es &#224; OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces classes fournissent plusieurs services, allant des exceptions aux entrées et sorties de fichier.  
  
 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)  
 Utilisé pour créer des éléments lorsque c'est demandé par d'autres conteneurs.  Cette classe sert de classe de base pour des types de fabriques, y compris `COleTemplateServer`.  
  
 [COleMessageFilter](../mfc/reference/colemessagefilter-class.md)  
 Sert à gérer la concurrence avec des appels de procédure distante légers \(LRPC\) OLE.  
  
 [COleStreamFile](../mfc/reference/colestreamfile-class.md)  
 Utilise l'interface COM `IStream` pour d'accéder aux fichiers `CFile` composites.  Cette classe \(dérivée de `CFile`\) permet à la sérialisation MFC d'utiliser le stockage structuré OLE.  
  
 [CRectTracker](../mfc/reference/crecttracker-class.md)  
 Utilisé pour permettre déplacer, redimensionner, et réorientater les éléments sur place.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)