---
title: "Cibles multiples | Microsoft Docs"
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
helpviewer_keywords: 
  - "makefiles, cible"
  - "cibles multiples dans NMAKE"
  - "cibles multiples dans NMAKE"
  - "Programme NMAKE, cible"
ms.assetid: b609a179-0b9f-4b08-9930-998047588ae0
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Cibles multiples
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE évalue plusieurs cibles dans une seule dépendance comme si chacune était spécifiée dans un bloc de description distinct.  
  
 Par exemple, ceci...  
  
```Output  
bounce.exe leap.exe : jump.obj  
   echo Building...  
```  
  
 .. .est évalué comme ceci :  
  
```Output  
bounce.exe : jump.obj  
   echo Building...  
leap.exe : jump.obj  
   echo Building...  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Cibles](../build/targets.md)