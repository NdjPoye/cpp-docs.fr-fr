---
title: "/LINENUMBERS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/linenumbers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LINENUMBERS (option Dumpbin)"
  - "numéros de ligne"
  - "LINENUMBERS (option Dumpbin)"
  - "-LINENUMBERS (option Dumpbin)"
ms.assetid: 1681d582-2c2f-484e-9920-109959549055
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /LINENUMBERS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LINENUMBERS  
```  
  
## Notes  
 Cette option affiche les numéros de ligne COFF.  Les numéros de ligne existent dans un fichier objet qui a été compilé à l'aide des options Base de données du programme \(\/Zi\), Compatible C7 \(\/Z7\) ou Numéros de ligne uniquement \(\/Zd\).  Les DLL et les fichiers exécutables contiennent des numéros de ligne COFF s'ils ont été liés à l'aide de l'option Générer les informations de débogage \(\/DEBUG\).  
  
 Seule l'option [\/HEADERS](../../build/reference/headers.md) de DUMPBIN est disponible pour les fichiers générés à l'aide de l'option de compilation [\/GL](../../build/reference/gl-whole-program-optimization.md).  
  
## Voir aussi  
 [Options DUMPBIN](../../build/reference/dumpbin-options.md)