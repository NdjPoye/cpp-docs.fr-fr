---
title: "regex_traits&lt;wchar_t&gt;, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::regex_traits<wchar_t>"
  - "regex_traits<wchar_t>"
  - "std.tr1.regex_traits<wchar_t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_traits<wchar_t>, classe [TR1]"
ms.assetid: 288d6fdb-fb8e-4a4d-904a-53916be7f95b
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# regex_traits&lt;wchar_t&gt;, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécialisation de regex\_traits pour wchar\_t.  
  
## Syntaxe  
  
```  
template <>  
    class regex_traits<wchar_t>  
```  
  
## Notes  
 La classe est une spécialisation explicite de la classe de modèle [Classe regex\_traits](../standard-library/regex-traits-class.md) pour les éléments de type `wchar_t` \(pour qu’elle puisse tirer parti des fonctions de bibliothèque qui manipulent des objets de ce type\).  
  
## Configuration requise  
 **En\-tête :** \<regex\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<regex\>](../standard-library/regex.md)   
 [Classe regex\_traits](../standard-library/regex-traits-class.md)