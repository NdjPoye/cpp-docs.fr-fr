---
title: "/RAWDATA | Microsoft Docs"
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
  - "/rawdata"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RAWDATA (option Dumpbin)"
  - "données brutes"
  - "RAWDATA (option Dumpbin)"
  - "-RAWDATA (option Dumpbin)"
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /RAWDATA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/RAWDATA[:{1|2|4|8|NONE[,number]]  
```  
  
## Notes  
 Cette option affiche le contenu brut de chaque section du fichier.  Les arguments déterminent le format de l'affichage, comme indiqué ci\-dessous :  
  
|Argument|Résultat|  
|--------------|--------------|  
|1|Valeur par défaut.  Le contenu est affiché sous la forme d'octets hexadécimaux et aussi sous la forme de caractères ASCII s'ils ont une représentation imprimée.|  
|2|Le contenu s'affiche sous la forme de valeurs hexadécimales codées sur deux octets.|  
|4|Le contenu s'affiche sous la forme de valeurs hexadécimales codées sur quatre octets.|  
|8|Le contenu s'affiche sous la forme de valeurs hexadécimales codées sur huit octets.|  
|NONE|Les données brutes sont supprimées.  Cet argument est utile pour contrôler la sortie de \/ALL.|  
|*Nombre*|Les lignes affichées sont définies à une largeur qui contient `number` valeurs par ligne.|  
  
 Seule l'option [\/HEADERS](../../build/reference/headers.md) de DUMPBIN est disponible pour les fichiers générés à l'aide de l'option de compilation [\/GL](../../build/reference/gl-whole-program-optimization.md).  
  
## Voir aussi  
 [Options DUMPBIN](../../build/reference/dumpbin-options.md)