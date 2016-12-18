---
title: "Design Principles for Collection and Enumerator Interfaces | Microsoft Docs"
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
  - "collection interfaces"
  - "enumerator interfaces"
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Design Principles for Collection and Enumerator Interfaces
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il existe des principes de conception derrière chaque type d'interface :  
  
-   Une interface de la collection fournit *l'accès aléatoire* en un *seul* élément dans la collection via la méthode de **Élément** , elle laisse les clients déterminer le nombre d'éléments dans la collection via la propriété de **Nombre** , et souvent permet aux clients d'ajouter et de supprimer des éléments.  
  
-   Une interface d'énumérateur fournit *l'accès séquentiel* *à plusieurs* éléments dans une collection, elle ne permet pas au client de déterminer le nombre d'éléments dans la collection \(jusqu'à ce que l'énumérateur cesse de retourner des éléments\) ; elle ne fournit aucun moyen d'ajouter ou de supprimer des éléments.  
  
 Chaque type d'interface joue un rôle différent en fournissant l'accès aux éléments dans une collection.  
  
## Voir aussi  
 [Collections et énumérateurs](../atl/atl-collections-and-enumerators.md)