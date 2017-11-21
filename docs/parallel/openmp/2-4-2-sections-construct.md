---
title: 2.4.2 construction sections | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 22aa4cc1bde59234d70803c2e878d3fbf83f499e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="242-sections-construct"></a>2.4.2 Construction sections
Le **sections** directive identifie une construction de partage de travail noniterative qui spécifie un jeu des constructions pour être réparti entre les threads dans une équipe. Chaque section est exécutée une fois par un thread dans l’équipe. La syntaxe de la **sections** la directive est la suivante :  
  
```  
#pragma omp sections [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block ]  
...  
}  
```  
  
 La clause est une des opérations suivantes :  
  
 **privé (** *variable-list* **)**  
  
 **firstprivate (** *variable-list* **)**  
  
 **lastprivate (** *variable-list* **)**  
  
 **la réduction (** *opérateur* **:***variable-list* **)**   
  
 **nowait**  
  
 Chaque section est précédée par un **section** directive, bien que le **section** la directive est facultative pour la première section. Le **section** directives doivent apparaître dans l’étendue lexicale de la **sections** directive. Il existe une barrière implicite à la fin d’un **sections** construire, sauf si un **nowait** est spécifié.  
  
 Restrictions à le **sections** directive sont les suivantes :  
  
-   A **section** directive ne doit pas figurer en dehors de l’étendue lexicale de la **sections** directive.  
  
-   Un seul **nowait** clause peut s’afficher dans un **sections** directive.  
  
## <a name="cross-references"></a>Références externes :  
  
-   **privé**, **firstprivate**, **lastprivate**, et **réduction** clauses, consultez [Section 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) page 25.