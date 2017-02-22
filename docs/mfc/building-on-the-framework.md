---
title: "G&#233;n&#233;ration &#224; partir du Framework | Microsoft Docs"
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
  - "infrastructure de l'application (C++), générer des applications"
  - "applications (MFC)"
  - "classes spécifiques à l'application (C++)"
  - "MFC (C++), développement de l'application"
ms.assetid: 883f0f19-866f-4221-8a3d-5607941dc8d0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# G&#233;n&#233;ration &#224; partir du Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Votre rôle lors de la configuration d'une application avec l'infrastructure MFC est de fournir le code source spécifique à l'application et de connecter les composants en définissant les messages et les commandes auxquels ils répondent.  Vous utilisez les techniques du langage C\+\+ et C\+\+ standard pour dériver vos propres classes spécifiques à l'application de celles fournies par la bibliothèque de classes et pour remplacer et augmenter le comportement de la classe de base.  
  
 Dans les rubriques connexes, les tableaux suivants indiquent la séquence générale d'opérations que vous suivrez généralement et les responsabilités par rapport aux responsabilités de l'infrastructure :  
  
-   [Séquence pour créer une application avec l'infrastructure](../mfc/sequence-of-operations-for-building-mfc-applications.md)  
  
-   [Ordre des opérations pour la création d'applications OLE](../mfc/sequence-of-operations-for-creating-ole-applications.md)  
  
-   [Ordre des opérations pour la création de contrôles ActiveX](../mfc/sequence-of-operations-for-creating-activex-controls.md)  
  
-   [Ordre des opérations pour la création d'applications de base de données](../mfc/sequence-of-operations-for-creating-database-applications.md)  
  
 Dans la plupart des cas, vous pouvez suivre ces tables comme une séquence d'étapes pour créer une application MFC, bien que certaines étapes sont des options alternatives.  Par exemple, la plupart des applications utilisent un type de classe d'affichage parmi les nombreux types disponibles.  
  
## Voir aussi  
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)