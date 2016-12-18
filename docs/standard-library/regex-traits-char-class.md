---
title: "regex_traits &lt; char &gt; (classe) | Microsoft Docs"
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
  - "std::tr1::regex_traits<char>"
  - "regex_traits<char>"
  - "std.tr1.regex_traits<char>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_traits < char > (classe) (TR1)"
ms.assetid: ce95ebcd-3687-4ad5-bf1d-b89fdc633675
caps.latest.revision: 17
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# regex_traits &lt; char &gt; (classe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécialisation de regex\_traits pour char.  
  
## Syntaxe  
  
```  
template <>  
    class regex_traits<char>  
```  
  
## Notes  
 La classe est une spécialisation explicite de la classe de modèle [Classe regex\_traits](../standard-library/regex-traits-class.md) pour les éléments de type `char` \(afin qu’il peut tirer parti des fonctions de bibliothèque qui manipulent des objets de ce type\).  
  
## Configuration requise  
 **En\-tête :** \<regex\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<regex\>](../standard-library/regex.md)   
 [Classe regex\_traits](../standard-library/regex-traits-class.md)