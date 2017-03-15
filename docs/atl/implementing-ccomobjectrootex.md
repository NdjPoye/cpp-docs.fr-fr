---
title: "Implementing CComObjectRootEx | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CComObjectRootEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectRoot class, implémenter"
  - "CComObjectRootEx class"
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Implementing CComObjectRootEx
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) est essentiel. Tous les objets ATL doivent avoir une instance de `CComObjectRootEx` ou de [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) dans leur héritage.  `CComObjectRootEx` fournit le mécanisme `QueryInterface` par défaut en fonction des entrées de la mappe COM.  
  
 Via sa mappe COM, les interfaces d'un objet sont exposées à un client quand celui\-ci émet une requête pour une interface.  La requête est effectuée via `CComObjectRootEx::InternalQueryInterface`.  `InternalQueryInterface` gère seulement des interfaces dans le tableau de mappage COM.  
  
 Vous pouvez entrer des interfaces dans le tableau de mappage COM avec la macro [COM\_INTERFACE\_ENTRY](../Topic/COM_INTERFACE_ENTRY%20\(ATL\).md) ou avec une de ses variantes.  Par exemple, le code suivant entre les interfaces `IDispatch`, `IBeeper` et `ISupportErrorInfo` dans le tableau de mappage COM :  
  
 [!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/CPP/implementing-ccomobjectrootex_1.h)]  
  
## Voir aussi  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)   
 [COM Map Macros](../atl/reference/com-map-macros.md)