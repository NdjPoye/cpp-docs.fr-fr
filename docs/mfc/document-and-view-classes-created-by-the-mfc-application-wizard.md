---
title: "Classes de document et de vue cr&#233;&#233;es par l&#39;Assistant Application MFC | Microsoft Docs"
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
  - "Assistants Application (C++), classes documents/vues créées"
  - "classes de documents"
  - "classes de documents, créées par les Assistants Application"
  - "classes vues, créées par les Assistants Application"
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de document et de vue cr&#233;&#233;es par l&#39;Assistant Application MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'Application MFC offre un avantage sur le développement de programmes lors de la création du document et les classes d'affichage squelettiques automatiquement.  Vous pouvez ensuite [commandes de mappage et messages à ces classes](../mfc/reference/mapping-messages-to-functions.md) et utiliser l'éditeur de code source Visual C\+\+ pour écrire les fonctions membres.  
  
 La classe de document créée par l'Application MFC est dérivée de la classe [CDocument](../mfc/reference/cdocument-class.md).  La classe d'affichage est dérivée de [CView](../mfc/reference/cview-class.md).  Les noms de l'Application fournit les classes et les fichiers qui contiennent les sont basés sur le nom du projet que vous fournissez dans la boîte de dialogue de l'Application.  Dans l'Application, vous pouvez utiliser la page générée de classes pour modifier le nom par défaut.  
  
 Certaines applications peuvent avoir besoin de plusieurs fichiers de document, la classe d'affichage, ou de la classe cadre de fenêtre.  Pour plus d'informations, consultez [Plusieurs types de document, vues, et fenêtres frames](../mfc/multiple-document-types-views-and-frame-windows.md).  
  
## Voir aussi  
 [Architecture document\/vue](../mfc/document-view-architecture.md)