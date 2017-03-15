---
title: "/LINKERMEMBER | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/linkermember"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LINKERMEMBER (option Dumpbin)"
  - "LINKERMEMBER (option Dumpbin)"
  - "-LINKERMEMBER (option Dumpbin)"
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /LINKERMEMBER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LINKERMEMBER[:{1|2}]  
```  
  
## Notes  
 Cette option affiche des symboles publics définis dans une bibliothèque.  Spécifiez l'argument 1 pour afficher des symboles dans un ordre d'objets, ainsi que leurs offsets.  Spécifiez l'argument 2 pour afficher les offsets et les numéros d'index des objets, puis lister les symboles dans un ordre alphabétique, ainsi que l'index objet de chacun d'eux.  Pour obtenir les deux types de sortie, spécifiez \/LINKERMEMBER dans l'argument du numéro.  
  
 Seule l'option [\/HEADERS](../../build/reference/headers.md) de DUMPBIN est disponible pour les fichiers générés à l'aide de l'option de compilation [\/GL](../../build/reference/gl-whole-program-optimization.md).  
  
## Voir aussi  
 [Options DUMPBIN](../../build/reference/dumpbin-options.md)