---
title: "Interfaces (ATL) | Microsoft Docs"
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
  - "interfaces COM"
  - "interfaces, COM"
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Interfaces (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une interface est la façon dont un objet expose ses fonctionnalités au monde externe.  Dans COM, une interface est un tableau de pointeurs \(comme C\+\+ vtable\) aux fonctions implémentées par l'objet.  Le tableau représente l'interface, et les fonctions à laquelle il pointe sont les méthodes de cette interface.  Un objet peut exposer autant d'interfaces qu'il choisit.  
  
 Chaque interface est basé sur l'interface COM fondamentale, [IUnknown](../atl/iunknown.md).  Les méthodes d' **IUnknown** permettent la navigation vers d'autres interfaces exposées par l'objet.  
  
 De plus, chaque interface reçoit un ID d'interface \(IID\).  Cette unicité le est facile de prendre en charge le versioning d'interface.  Une nouvelle version d'une interface est simplement une nouvelle interface, avec un nouvel IID.  
  
> [!NOTE]
>  Les IID pour COM standard et les interfaces OLE sont intégrés.  
  
## Voir aussi  
 [Introduction to COM](../atl/introduction-to-com.md)   
 [COM Objects and Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms690343)