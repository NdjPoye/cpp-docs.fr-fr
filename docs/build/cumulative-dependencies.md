---
title: "D&#233;pendances cumulatives | Microsoft Docs"
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
  - "dépendances cumulatives"
  - "dépendances cumulatives dans NMAKE"
  - "dépendances"
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;pendances cumulatives
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les dépendances sont cumulées dans un bloc de description si la cible se répète.  
  
 Par exemple, ce groupe de règles,  
  
```Output  
bounce.exe : jump.obj  
bounce.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 est évaluée comme ceci :  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 Cibles multiples dans plusieurs lignes de dépendance dans un bloc de description unique sont évaluées comme si chacune était spécifiée dans un bloc de description distinct, mais les cibles qui ne sont pas dans la dernière ligne de dépendance n’utilisent pas le bloc de commandes. NMAKE tente d’utiliser une règle d’inférence pour ces cibles.  
  
 Par exemple, ce groupe de règles,  
  
```Output  
leap.exe bounce.exe : jump.obj  
bounce.exe climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 est évaluée comme ceci :  
  
```Output  
  
leap.exe : jump.obj  
# invokes an inference rule  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Cibles](../build/targets.md)