---
title: "2.7.2 Data-Sharing Attribute Clauses | Microsoft Docs"
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
ms.assetid: 47347d3c-18bd-441f-99cf-7737564c417f
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2 Data-Sharing Attribute Clauses
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Plusieurs directives acceptent les clauses qui permettent à un utilisateur de contrôler les attributs de partage des variables pour la durée de la zone.  En partageant les clauses d'attribut applique uniquement aux variables dans l'étendue lexicale de la directive sur laquelle la clause apparaît.  Il permet toutes les clauses suivantes sur les directives.  La liste des clauses valides sur une directive particulière sont décrites avec la directive.  
  
 Si une variable est visible lorsqu'un parallèle ou élément de partage de travail est produit, et la variable n'est pas spécifiée dans une clause d'attribut de partage ou directive de **threadprivate** , la variable est partagée.  Les variables statiques déclarées dans l'étendue dynamique d'une région parallèle partagées.  Amassez la mémoire allouée \(par exemple, l'utilisation **malloc \(\)** en C ou C\+\+ ou l'opérateur de **nouveau** en C\+\+\) est partagé.  \(Le pointeur à cette mémoire, toutefois, peuvent être privés ou partagés.\) Les variables avec la durée automatique de stockage déclarée dans l'étendue dynamique d'une région parallèle sont privées.  
  
 La plupart des clauses reçoivent un argument *de variable\-liste* , qui est une liste avec la virgule comme séparateur des variables qui sont visibles.  Si une variable référencée dans une clause d'attribut de partage de données a un type dérivé à partir d'un modèle, sans aucune autre référence à la variable du programme, le comportement n'est pas défini.  
  
 toutes les variables qui apparaissent dans les clauses directives doivent être visibles.  Les clauses peuvent être répétées si nécessaire, mais aucune variable ne peut être spécifiée dans plusieurs clause, sauf qu'une variable peut être spécifiée dans **firstprivate** et une clause d' **elle** .  
  
 les sections suivantes décrivent les clauses d'attribut de partage de données :  
  
-   **privé**, [section 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) à la page 25.  
  
-   **firstprivate**, [section 2.7.2.2](../../parallel/openmp/2-7-2-2-firstprivate.md) à la page 26.  
  
-   **elle**, [section 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) à la page 27.  
  
-   **partagé**, [section 2.7.2.4](../../parallel/openmp/2-7-2-4-shared.md) à la page 27.  
  
-   **valeur par défaut**, [section 2.7.2.5](../../parallel/openmp/2-7-2-5-default.md) à la page 28.  
  
-   **réduction**, [section 2.7.2.6](../../parallel/openmp/2-7-2-6-reduction.md) à la page 28.  
  
-   **copyin**, [section 2.7.2.7](../../parallel/openmp/2-7-2-7-copyin.md) à la page 31.  
  
-   **copyprivate**, [section 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) à la page 32.