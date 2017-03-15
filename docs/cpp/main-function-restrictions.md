---
title: "Restrictions relatives &#224; la fonction main | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Main"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main (fonction), limitations sur l'utilisation"
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Restrictions relatives &#224; la fonction main
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Plusieurs restrictions qui s'appliquent à la fonction **main** ne s'appliquent à aucune autre fonction C\+\+.  La fonction **main** :  
  
-   ne peut pas être surchargée \(consultez [Surcharge](../misc/overloading-cpp.md)\) ;  
  
-   ne peut pas être déclarée comme **inline** ;  
  
-   ne peut pas être déclarée comme **static** ;  
  
-   son adresse ne peut pas être prise.  
  
-   Ne peut pas être appelé.  
  
## Voir aussi  
 [main : démarrage du programme](../cpp/main-program-startup.md)