---
title: "char_traits&lt;wchar_t&gt;, struct | Microsoft Docs"
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
  - "std.char_traits<wchar_t>"
  - "char_traits<wchar_t>"
  - "string/std::char_traits<wchar_t>"
  - "std::char_traits<wchar_t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<wchar_t> (classe)"
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# char_traits&lt;wchar_t&gt;, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe qui est une spécialisation de la structure de modèle **char\_traits\<CharType\>** vers un élément de type `wchar_t`.  
  
## Syntaxe  
  
```  
template<> struct char_traits<wchar_t>;  
```  
  
## Notes  
 La spécialisation permet à la structure d'exploiter les fonctions de la bibliothèque qui manipulent des objets de ce type `wchar_t`.  
  
## Configuration requise  
 **En\-tête :** \<chaîne\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [char\_traits, struct](../standard-library/char-traits-struct.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)