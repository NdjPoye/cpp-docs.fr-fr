---
title: "SDI et MDI | Microsoft Docs"
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
  - "fenêtres frame, applications MDI"
  - "fenêtres frame, applications SDI"
  - "MDI, différences par rapport à SDI"
  - "MFC, fenêtres"
  - "interface monodocument, applications"
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SDI et MDI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC rend plus facile de travailler avec à la fois des applications interfaces de monodocuments \(SDI\) et des applications interfaces de documents multiples \(MDI\).  
  
 Les applications SDI permettent qu'une unique fenêtre cadre soit ouverte à la fois.  Les applications MDI permettent à plusieurs fenêtres cadre d'être ouvertes dans la même instance d'une application.  Une application MDI a une fenêtre dans laquelle plusieurs fenêtres enfants MDI, qui sont des fenêtres cadres elles\-mêmes, peuvent être ouvertes, chacune contenant un document distinct.  Dans certaines applications, les fenêtres enfants peuvent être de types différents, tels que les fenêtres de graphique et la fenêtre de feuille de calcul.  Dans ce cas, la barre de menus peut changer à mesure que les fenêtres enfants MDI de différents types sont activées.  
  
> [!NOTE]
>  Sous Windows 95 et versions ultérieures, les applications sont généralement SDI car le système d'exploitation a adopté une vue « centré sur les documents ».  
  
 Pour plus d'informations, consultez [Documents, vues, et le .NET Framework](../mfc/documents-views-and-the-framework.md).  
  
## Voir aussi  
 [Utilisation des classes pour l'écriture d'applications pour Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)