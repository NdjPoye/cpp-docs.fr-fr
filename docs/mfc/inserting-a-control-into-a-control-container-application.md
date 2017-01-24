---
title: "Conteneurs de contr&#244;les ActiveX&#160;: insertion d&#39;un contr&#244;le dans une application de conteneur de contr&#244;le | Microsoft Docs"
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
  - "conteneurs de contrôles ActiveX (C++), insérer des contrôles"
  - "contrôles ActiveX (C++), ajouter aux projets"
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conteneurs de contr&#244;les ActiveX&#160;: insertion d&#39;un contr&#244;le dans une application de conteneur de contr&#244;le
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Avant de pouvoir accéder à un contrôle ActiveX d'une application au conteneur de contrôles ActiveX, vous devez ajouter le contrôle ActiveX à l'application conteneur dans la boîte de dialogue de [Contrôle ActiveX d'insertion](../mfc/insert-activex-control-dialog-box.md).  
  
 Pour ajouter un contrôle ActiveX au projet de conteneur de contrôles ActiveX, consultez [Contrôles ActiveX de visualisation et d'ajout dans une boîte de dialogue](../mfc/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
 Une fois que vous ajoutez le contrôle, vous devez ajouter une variable membre \(du type de contrôle ActiveX\) à la classe de la boîte de dialogue.  Pour plus d'informations sur cette procédure, consultez [Ajout d'une variable membre](../ide/adding-a-member-variable-visual-cpp.md).  
  
 Une fois que vous avez ajouté la variable membre, une classe, appelée classe wrapper, est automatiquement créée et ajoutée à votre projet.  Cette classe est utilisée comme interface entre le conteneur de contrôle et le contrôle incorporé.  
  
## Voir aussi  
 [Conteneurs de contrôles ActiveX](../mfc/activex-control-containers.md)