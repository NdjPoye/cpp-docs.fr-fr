---
title: "2.7.2.7 copyin | Microsoft Docs"
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
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.7 copyin
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La clause de **copyin** fournit un mécanisme pour assigner la même valeur aux variables de **threadprivate** pour chaque thread dans l'équipe qui exécute la région parallèle.  Pour chaque variable spécifiée dans une clause de **copyin** , la valeur de la variable dans le thread principal de l'équipe est copiée, comme si par assignation, des copies de thread privé au début de la zone parallèle.  La syntaxe de la clause de **copyin** est la suivante :  
  
```  
  
copyin(  
variable-list  
)  
  
```  
  
 Les restrictions sur la clause de **copyin** sont les suivantes :  
  
-   Une variable spécifiée dans la clause de **copyin** doit avoir un opérateur d'assignation de copie accessible et pas ambigu.  
  
-   Une variable spécifiée dans la clause de **copyin** doit être une variable de **threadprivate** .