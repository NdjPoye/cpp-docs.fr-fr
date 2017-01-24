---
title: "Acc&#232;s &#224; la biblioth&#232;que de types | Microsoft Docs"
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
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bibliothèques de types, accéder"
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 14
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Acc&#232;s &#224; la biblioth&#232;que de types
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les bibliothèques de type exposent des interfaces d'un contrôle OLE à d'autres applications OLE\- averties.  Chaque contrôle OLE doit avoir une bibliothèque de types si un ou plusieurs interfaces doivent être exposées.  
  
 Les macros suivantes permettent un contrôle de l'OLE qui permet d'accéder à sa propre bibliothèque de types :  
  
### Accès à la bibliothèque de types  
  
|||  
|-|-|  
|[DECLARE\_OLETYPELIB](../Topic/DECLARE_OLETYPELIB.md)|Déclare une fonction membre de `GetTypeLib` d'un contrôle OLE \(doit être utilisé dans la déclaration de classe\).|  
|[IMPLEMENT\_OLETYPELIB](../Topic/IMPLEMENT_OLETYPELIB.md)|Implémente une fonction membre de `GetTypeLib` d'un contrôle OLE \(doit être utilisé dans l'implémentation de classe\).|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)