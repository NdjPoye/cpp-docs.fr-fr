---
title: "&lt;iostream&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<iostream>"
  - "std::<iostream>"
  - "<iostream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iostream (en-tête)"
ms.assetid: de5d39e1-7e77-4b55-bcd1-7c77b41515c8
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# &lt;iostream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Déclare des objets qui contrôlent la lecture et l'écriture des flux standard.  Il s'agit souvent du seul en\-tête que vous devez inclure pour effectuer l'entrée et la sortie à partir d'un programme C\+\+.  
  
## Syntaxe  
  
```  
  
#include <iostream>  
  
```  
  
## Notes  
 Les objets se répartissent en deux groupes :  
  
-   [cin](../Topic/cin.md), [cout](../Topic/cout.md), [cerr](../Topic/cerr.md) et [clog](../Topic/clog.md) sont orientés octets et effectuent des transferts conventionnels de type « un octet à la fois ».  
  
-   [wcin](../Topic/wcin.md), [wcout](../Topic/wcout.md), [wcerr](../Topic/wcerr.md) et [wclog](../Topic/wclog.md) sont orientés largeur et traduisent vers et à partir des caractères larges que le programme manipule en interne.  
  
 Une fois que vous avez effectué certaines opérations sur un flux, telles que l'entrée standard, vous ne pouvez plus effectuer d'opérations d'une orientation différente sur le même flux.  Ainsi, un programme ne peut pas opérer indifféremment à la fois sur [cin](../Topic/cin.md) et sur [wcin](../Topic/wcin.md), par exemple.  
  
 Tous les objets déclarés dans cet en\-tête partagent une propriété particulière : vous pouvez partir du principe qu'ils sont construits avant tout objet statique que vous définissez, dans une unité de traduction qui inclut \<iostream\>.  De même, vous pouvez partir du principe que ces objets ne sont pas détruits avant les destructeurs pour tout objet statique de ce genre que vous définissez.  \(Les flux de sortie, cependant, sont vidés durant l'arrêt du programme.\) Par conséquent, vous pouvez sans risque lire ou écrire dans les flux standard avant le démarrage et après l'arrêt du programme.  
  
 Cette garantie n'est cependant pas universelle.  Un constructeur statique peut appeler une fonction dans une autre unité de traduction.  La fonction appelée ne peut pas partir du principe que les objets déclarés dans cet en\-tête ont été construits, étant donné l'ordre incertain dans lequel les unités de traduction participent à la construction statique.  Pour utiliser ces objets dans ce contexte, vous devez d'abord construire un objet de classe [ios\_base::Init](../Topic/ios_base::Init.md).  
  
### Objets de flux global  
  
|||  
|-|-|  
|[cerr](../Topic/cerr.md)|Spécifie le flux global `cerr`.|  
|[cin](../Topic/cin.md)|Spécifie le flux global `cin`.|  
|[clog](../Topic/clog.md)|Spécifie le flux global `clog`.|  
|[cout](../Topic/cout.md)|Spécifie le flux global `cout`.|  
|[wcerr](../Topic/wcerr.md)|Spécifie le flux global `wcerr`.|  
|[wcin](../Topic/wcin.md)|Spécifie le flux global `wcin`.|  
|[wclog](../Topic/wclog.md)|Spécifie le flux global `wclog`.|  
|[wcout](../Topic/wcout.md)|Spécifie le flux global `wcout`.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)