---
title: "IUnknown | Microsoft Docs"
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
  - "IUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interfaces COM, base interface"
  - "IUnknown interface"
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IUnknown
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) est l'interface de base de chaque autre interface COM.  Cette interface définit trois méthodes : [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521), [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), et [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317).  [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) permet à un utilisateur d'interface de demander à l'objet un pointeur vers une autre de ses interfaces.  [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) et [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) implémentent le décompte de références sur l'interface.  
  
## Voir aussi  
 [Introduction to COM](../atl/introduction-to-com.md)   
 [IUnknown and Interface Inheritance](http://msdn.microsoft.com/library/windows/desktop/ms692713)