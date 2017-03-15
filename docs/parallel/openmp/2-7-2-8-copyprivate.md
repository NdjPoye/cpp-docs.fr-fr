---
title: "2.7.2.8 copyprivate | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: c382348c-c785-45b2-8ee6-a66b76b97f3e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.8 copyprivate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La clause de **copyprivate** fournit un mécanisme pour utiliser une variable privée pour diffuser une valeur d'un membre d'une équipe aux autres membres.  Il s'agit d'une alternative à utiliser une variable partagée pour la valeur lorsque la fourniture d'une variable si partagée serait difficile \(par exemple, dans une récursivité requérant une variable différente à chaque niveau\).  La clause de **copyprivate** peuvent seulement apparaître sur la directive d' **unique** .  
  
 La syntaxe de la clause de **copyprivate** est la suivante :  
  
```  
  
copyprivate(  
variable-list  
)  
  
```  
  
 L'effet de la clause de **copyprivate** sur les variables dans sa variable\-liste se produit une fois que l'exécution du bloc structuré associé à l'élément d' **unique** , et avant que les threads de l'dans l'équipe aient laissé le cloisonnement à la fin de l'élément.  Puis, en tous les autres threads de l'équipe, pour chaque variable dans *la variable\-liste*, que la variable est définie \(comme si par assignation\) avec la valeur de la variable correspondante dans le thread qui a exécuté le bloc structuré de l'élément.  
  
 Les restrictions sur la clause de **copyprivate** sont les suivantes :  
  
-   Une variable spécifiée dans la clause de **copyprivate** ne doit pas apparaître dans une clause de **privé** ou de **firstprivate** pour la même directive d' **unique** .  
  
-   Si une directive d' **unique** avec une clause de **copyprivate** est produite dans l'étendue dynamique d'une région parallèle, toutes les variables spécifiées dans la clause de **copyprivate** doivent être privées dans le contexte englobant.  
  
-   Une variable spécifiée dans la clause de **copyprivate** doit avoir un opérateur d'assignation de copie pas ambigu accessible.