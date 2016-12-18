---
title: "Using the RichEdit 1.0 Control with MFC | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "RichEdit 1.0 control"
  - "rich edit controls, RichEdit 1.0"
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Using the RichEdit 1.0 Control with MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour utiliser un contrôle RichEdit, vous devez d'abord appeler [AfxInitRichEdit2](../Topic/AfxInitRichEdit2.md) pour charger le contrôle RichEdit 2.0 \(RICHED20.DLL\) ou [AfxInitRichEdit](../Topic/AfxInitRichEdit.md) pour charger l'ancien contrôle RichEdit 1.0 \(RICHED32.DLL\).  
  
 Vous pouvez utiliser la classe actuelle [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) avec l'ancien contrôle RichEdit 1.0, mais **CRichEditCtrl** n'est conçu que pour prendre en charge le contrôle RichEdit 2.0.  Dans la mesure où RichEdit 1.0 et RichEdit 2.0 sont très similaires, la plupart des méthodes fonctionneront ; cependant, il existe des différences entre les contrôles 1.0 et 2.0, et certaines méthodes peuvent ne pas fonctionner correctement ou simplement ne pas fonctionner.  
  
## Configuration requise  
 MFC  
  
## Voir aussi  
 [Troubleshooting the Dialog Editor](../mfc/troubleshooting-the-dialog-editor.md)   
 [Dialog Editor](../mfc/dialog-editor.md)