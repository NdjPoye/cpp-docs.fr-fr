---
title: "char_traits&lt;char32_t&gt;, struct | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "string/std::char_traits<char_32t>"
  - "char_traits<char32_t>"
  - "std.char_traits<char_32t>"
  - "std::char_traits<char_32t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<char32_t> (classe)"
ms.assetid: c0315466-45d0-4a99-b83e-3b1dbfbfbbc3
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# char_traits&lt;char32_t&gt;, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une structure qui est une spécialisation de structure **char\_traits\<CharType\>** de modèle à un élément de type `char32_t`.  
  
## Syntaxe  
  
```  
template<> struct char_traits<char32_t>;  
```  
  
## Notes  
 La spécialisation structure permet à d'exploiter les fonctions de la bibliothèque qui manipulent des objets de ce type `char32_t`.  
  
## Configuration requise  
 **En\-tête :** \<chaîne\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<string\>](../standard-library/string.md)   
 [char\_traits, struct](../standard-library/char-traits-struct.md)