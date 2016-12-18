---
title: "Cr&#233;ation de mod&#232;le de document | Microsoft Docs"
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
  - "constructeurs [C++], modèle de document"
  - "modèles de document"
  - "modèles de document, créer"
  - "MFC, modèles de document"
  - "modèles, modèles de document"
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
caps.latest.revision: 9
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation de mod&#232;le de document
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous créez un document en réponse à une commande `New` ou de **Ouvrir** dans le menu de **Fichier**, le modèle de document crée également une nouvelle fenêtre frame dans laquelle afficher le document.  
  
 Le constructeur modèle de document spécifie les types de documents, les fenêtres, et de vues le modèle peut créer.  Cela est déterminé par les arguments que vous passez au constructeur modèle de document.  Le code suivant illustre la création d'un [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) pour un exemple d'application :  
  
 [!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/CPP/document-template-creation_1.cpp)]  
  
 Le pointeur vers un nouvel objet `CMultiDocTemplate` est utilisée comme argument à [AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md).  Les arguments du constructeur de `CMultiDocTemplate` incluent l'ID de ressource associé aux menus et des accélérateurs du type de document, ainsi que trois utilisation de la macro [RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md).  `RUNTIME_CLASS` retourne l'objet [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) pour la classe C\+\+ nommée comme argument.  Les trois objets `CRuntimeClass` passés au constructeur de modèle de document fournissent les informations nécessaires pour créer de nouveaux objets des classes spécifiées pendant la création de document.  L'exemple illustre la création d'un modèle de document qui crée des objets `CScribDoc` avec des objets `CScribView` joints.  Les vues sont encadrées par des fenêtres enfants MDI cadre standard.  
  
## Voir aussi  
 [Modèles de document et processus de création de document\/vue](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Création d'un document\/d'une vue](../mfc/document-view-creation.md)   
 [Relations entre les objets MFC](../mfc/relationships-among-mfc-objects.md)   
 [Création de documents, fenêtres et vues](../mfc/creating-new-documents-windows-and-views.md)