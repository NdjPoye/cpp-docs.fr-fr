---
title: "lastprivate | Microsoft Docs"
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
  - "lastprivate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lastprivate OpenMP clause"
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# lastprivate
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Spécifie que la version englobante du contexte de la variable est égal défini à la version privée de n'importe quel thread exécute l'itération finale \(élément de la boucle\) ou la dernière section \(sections \#pragma\).  
  
## Syntaxe  
  
```  
lastprivate(var)  
```  
  
## Notes  
 où,  
  
 `var`  
 La variable dont est égale défini à la version privée n'importe quel thread exécute l'itération finale \(élément de la boucle\) ou la dernière section \(sections \#pragma\).  
  
## Notes  
 `lastprivate` s'applique aux directives suivantes :  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Pour plus d'informations, consultez [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).  
  
## Exemple  
 Consultez [schedule](../../../parallel/openmp/reference/schedule.md) pour obtenir un exemple de clause d'utilisation `lastprivate` .  
  
## Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)