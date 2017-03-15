---
title: "2.4.2 sections Construct | Microsoft Docs"
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
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4.2 sections Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La directive de **sections** identifie un élément noniterative de partage de travail qui spécifie un ensemble d'éléments qui doivent être divisées entre les threads dans une équipe.  chaque section est exécutée une fois par un thread dans l'équipe.  La syntaxe de la directive de **sections** est la suivante :  
  
```  
#pragma omp sections [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-line  
      structured-block ]  
...  
}  
```  
  
 La clause est l'une des opérations suivantes :  
  
 *variable\-liste* **\)**de**privé \(**  
  
 *variable\-liste* **\)**de**firstprivate \(**  
  
 *variable\-liste* **\)**d'**elle \(**  
  
 *variable\-liste* **\)**de**Numéro de téléphone :** d'*opérateur de***réduction \(**  
  
 **nowait**  
  
 chaque section est précédée par une directive de **section** , bien que la directive de **section** soit facultative pour la première section.  Les directives de **section** doivent apparaître dans l'étendue lexicale de la directive de **sections** .  Il existe un cloisonnement implicite à la fin d'un élément de **sections** , à moins que **nowait** soit spécifié.  
  
 Les restrictions à la directive de **sections** sont les suivantes :  
  
-   Une directive de **section** ne doit pas apparaître à l'extérieur de l'étendue lexicale de la directive de **sections** .  
  
-   Uniquement une clause unique de **nowait** peut apparaître sur une directive de **sections** .  
  
## Références croisées :  
  
-   **privé**, **firstprivate**, **elle**, et les clauses de **réduction** , consultez [section 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) à la page 25.