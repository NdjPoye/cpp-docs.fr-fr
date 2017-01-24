---
title: "2.6.1 master Construct | Microsoft Docs"
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
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.1 master Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La directive de **page maître** identifie un élément qui spécifie un bloc structuré exécuté par le thread principal de l'équipe.  La syntaxe de la directive de **page maître** est la suivante :  
  
```  
#pragma omp master new-line  
   structured-block  
```  
  
 D'autres threads dans l'équipe n'exécutent pas le bloc structuré associé.  Il n'y a pas de cloisonnement implicite sur l'entrée à ou la sortie du principal élément.