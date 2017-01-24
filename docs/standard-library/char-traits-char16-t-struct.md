---
title: "char_traits&lt;char16_t&gt;, struct | Microsoft Docs"
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
  - "std::char_traits<char16_t>"
  - "std.char_traits<char16_t>"
  - "char_traits<char16_t>"
  - "string/std::char_traits<char16_t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<char16_t> (classe)"
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# char_traits&lt;char16_t&gt;, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un struc qui est une spécialisation de la structure de modèle **char\_traits\<CharType\>** vers un élément de type `char16_t`.  
  
## Syntaxe  
  
```  
template<> struct char_traits<char16_t>;  
```  
  
## Notes  
 La spécialisation permet à la structure d'exploiter les fonctions de la bibliothèque qui manipulent des objets du type `char16_t`.  
  
## Configuration requise  
 **En\-tête :** \<chaîne\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<string\>](../standard-library/string.md)   
 [char\_traits, struct](../standard-library/char-traits-struct.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)