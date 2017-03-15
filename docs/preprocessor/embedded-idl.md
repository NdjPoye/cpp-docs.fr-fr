---
title: "embedded_idl | Microsoft Docs"
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
  - "embedded_idl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "embedded_idl (attribut)"
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# embedded_idl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Indique que la bibliothèque de types est écrite dans le fichier .tlh et que le code généré par attributs est conservé.  
  
## Syntaxe  
  
```  
embedded_idl[("param")]  
```  
  
#### Paramètres  
 `param`  
 Peut avoir l'une des deux valeurs suivantes :  
  
-   emitidl : les informations de type importées à partir du typelib seront présentes dans le fichier IDL généré pour le projet avec attributs.  Il s'agit de la valeur par défaut qui sera appliquée si vous ne spécifiez pas de paramètre pour `embedded_idl`.  
  
-   no\_emitidl : les informations de type importées à partir du typelib ne seront pas présentes dans le fichier IDL généré pour le projet avec attributs.  
  
## Exemple  
  
```  
// import_embedded_idl.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib2")];  
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")  
```  
  
## Notes  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)