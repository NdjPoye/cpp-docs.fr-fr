---
title: "&lt;ccomplex&gt; | Microsoft Docs"
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
  - "<ccomplex>"
dev_langs: 
  - "C++"
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;ccomplex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Inclut l'en\-tête STL [\<complex\>](../standard-library/complex.md), qui inclut en réalité l'en\-tête \<complex.h\> de la bibliothèque C standard et ajoute les noms associés à l'espace de noms `std`.  
  
## Syntaxe  
  
```cpp  
  
#include <ccomplex>  
  
```  
  
## Notes  
 L'inclusion de cet en\-tête garantit également que les noms déclarés à l'aide d'une liaison externe dans l'en\-tête de la bibliothèque C standard soient déclarés dans l'espace de noms `std`.  
  
 Le nom `clog`, qui est déclaré dans \<complex.h\>, n'est pas défini dans l'espace de noms `std` en raison de conflits potentiels avec le nom `clog` qui est déclaré dans [\<iostream\>](../standard-library/iostream.md).  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Vue d'ensemble de la bibliothèque STL](../standard-library/cpp-standard-library-overview.md)