---
title: "tlbid | Microsoft Docs"
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
  - "tlbid"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tlbid (attribut)"
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tlbid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Permet de charger des bibliothèques autres que la bibliothèque de types principale.  
  
## Syntaxe  
  
```  
tlbid(number)  
```  
  
#### Paramètres  
 `number`  
 Numéro de la bibliothèque de types dans `filename`.  
  
## Notes  
 Si plusieurs bibliothèques de types sont générées dans une même DLL, il est possible de charger des bibliothèques autres que la bibliothèque de types primaires à l'aide de `tlbid`.  
  
 Par exemple :  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
 équivaut à :  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)