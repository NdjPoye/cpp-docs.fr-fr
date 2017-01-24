---
title: "A.6   Using the lastprivate Clause | Microsoft Docs"
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
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.6   Using the lastprivate Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'exécution correcte parfois dépend de la valeur que la dernière itération d'une boucle assigner à une variable.  De tels programmes doivent répertorier toutes les variables telles que des arguments à une clause d' `lastprivate` \([section 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) à la page 27\) afin que les valeurs des variables sont les mêmes que lorsque la boucle est exécutée de manière séquentielle.  
  
```  
#pragma omp parallel  
{  
   #pragma omp for lastprivate(i)  
      for (i=0; i<n-1; i++)  
         a[i] = b[i] + b[i+1];  
}  
a[i]=b[i];  
```  
  
 Dans l'exemple précédent, la valeur d' `i` à la fin de la zone parallèle sera égal `n–1`, comme dans le cas séquentiel.