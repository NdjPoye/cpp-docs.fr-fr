---
title: "is_error_code_enum, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "system_error/std::is_error_code_enum"
  - "std.is_error_code_enum"
  - "is_error_code_enum"
  - "std::is_error_code_enum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_error_code_enum (classe)"
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# is_error_code_enum, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un attribut de type qui détermine l'énumération d'[error\_code](../standard-library/error-code-class.md).  
  
## Syntaxe  
  
```  
template<_Enum>  
    class is_error_code_enum;  
```  
  
## Notes  
 Une instance de cet [attribut de type](../standard-library/type-traits.md) contient la valeur true si le type `_Enum` est une valeur d'énumération appropriée pour inscrire dans un objet de type `error_code`.  
  
 Il est autorisé à ajouter des spécialisations à ce type des types définis par l'utilisateur.  
  
## Configuration requise  
 **Header:** \<system\_error\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [\<system\_error\>](../standard-library/system-error.md)