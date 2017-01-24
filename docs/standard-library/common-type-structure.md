---
title: "common_type, structure | Microsoft Docs"
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
  - "chrono/std::common_type"
dev_langs: 
  - "C++"
ms.assetid: 2b42722c-c3dc-4d62-8613-0271e52b6f00
caps.latest.revision: 13
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# common_type, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit les spécialisations de classe de modèle [common\_type](../standard-library/common-type-class.md) pour les instanciations de [durée](../standard-library/duration-class.md) et de [time\_point](../standard-library/time-point-class.md).  
  
## Syntaxe  
  
```  
template<class Rep1, class Period1,  
   class Rep2, class Period2>  
struct common_type  
<chrono::duration<Rep1, Period1>,   
chrono::duration<Rep2, Period2>>;  
  
template<class Clock,  
   class Duration1, class Duration2>  
struct common_type  
<chrono::time_point<Clock, Duration1>,  
chrono::time_point<Clock, Duration2>>;  
```  
  
## Configuration requise  
 **En\-tête :** chrono  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)