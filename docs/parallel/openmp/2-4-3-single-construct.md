---
title: "2.4.3 single Construct | Microsoft Docs"
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
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4.3 single Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La directive d' **unique** identifie un élément qui spécifie que le bloc de type associé est exécuté par un seul thread dans l'équipe \(pas nécessairement le thread principal\).  La syntaxe de la directive d' **unique** est la suivante :  
  
```  
#pragma omp single [clause[[,] clause] ...] new-line  
   structured-block  
```  
  
 La clause est l'une des opérations suivantes :  
  
 *variable\-liste* **\)**de**privé \(**  
  
 *variable\-liste* **\)**de**firstprivate \(**  
  
 *variable\-liste* **\)**de**copyprivate \(**  
  
 **nowait**  
  
 Il existe un cloisonnement implicite après l'élément d' **unique** à moins qu'une clause de **nowait** soit spécifiée.  
  
 Les restrictions à la directive d' **unique** sont les suivantes :  
  
-   Uniquement une clause unique de **nowait** peut apparaître sur une directive d' **unique** .  
  
-   la clause de **copyprivate** ne doit pas être utilisée avec la clause de **nowait** .  
  
## Références croisées :  
  
-   **privé**, **firstprivate**, et les clauses de **copyprivate** , consultez [section 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) à la page 25.