---
title: "raw_dispinterfaces | Microsoft Docs"
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
  - "raw_dispinterfaces"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "raw_dispinterfaces (attribut)"
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# raw_dispinterfaces
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Indique au compilateur de générer des fonctions wrapper de bas niveau pour les méthodes et les propriétés dispinterface qui appellent **IDispatch::Invoke** et retournent le code d'erreur `HRESULT`.  
  
## Syntaxe  
  
```  
raw_dispinterfaces  
```  
  
## Notes  
 Si cet attribut n'est pas spécifié, seuls sont générés les wrappers de niveau supérieur, qui lèvent des exceptions C\+\+ en cas d'échec.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)