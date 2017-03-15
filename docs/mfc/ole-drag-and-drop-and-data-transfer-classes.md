---
title: "Classes de glisser-d&#233;placer OLE et de transfert de donn&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "transfert de données (C++), OLE"
  - "classes de transfert de données (C++)"
  - "glisser-déplacer (C++), classes"
  - "glisser-déplacer OLE (C++), et classes de transfert de données"
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Classes de glisser-d&#233;placer OLE et de transfert de donn&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces classes sont utilisées dans les transferts de données OLE.  Elles permettent de transférer des données entre applications à l'aide du presse\-papiers ou par le biais du glisser\-déplacer.  
  
 [COleDropSource](../mfc/reference/coledropsource-class.md)  
 Contrôle l'opération de glisser\-déplacer du début à la fin.  Cette classe détermine le démarrage et la fin de l'opération glisser\-déplacer.  Elle affiche également des informations sur le curseur pendant l'opération de glisser\-déplacer.  
  
 [COleDataSource](../mfc/reference/coledatasource-class.md)  
 Utilisé lorsqu'une application fournit des données pour un transfert de données.  `COleDataSource` peut être vu comme un objet presse\-papiers orienté\-objet.  
  
 [COleDropTarget](../mfc/reference/coledroptarget-class.md)  
 Représente la cible de l'opération de glisser\-déplacer.  Un objet `COleDropTarget` correspond à une fenêtre de l'écran.  Cela détermine s'il faut accepter les données "lâchées" sur lui et implémente l'opération de "lâcher".  
  
 [COleDataObject](../mfc/reference/coledataobject-class.md)  
 Utilisé en tant que coté récepteur à `COleDataSource`.  les objets `COleDataObject` permettent d'accéder aux données stockées dans un objet `COleDataSource`.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)