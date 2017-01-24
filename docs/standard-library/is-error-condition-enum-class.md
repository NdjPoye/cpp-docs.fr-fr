---
title: "is_error_condition_enum, classe | Microsoft Docs"
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
  - "std::is_error_condition_enum"
  - "std.is_error_condition_enum"
  - "is_error_condition_enum"
  - "system_error/std::is_error_condition_enum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_error_condition_enum (classe)"
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_error_condition_enum, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un attribut de type qui détermine l'énumération pour [error\_condition](../standard-library/error-condition-class.md).  
  
## Syntaxe  
  
```  
template<_Enum>  
    class is_error_condition_enum;  
```  
  
## Notes  
 Une instance de cet [attribut de type](../standard-library/type-traits.md) contient la valeur true si le type `_Enum` est une valeur d'énumération appropriée pour inscrire dans un objet de type `error_condition`.  
  
 Il est autorisé d'ajouter des spécialisations à ce type pour des types définis par l'utilisateur.  
  
## Configuration requise  
 **Header:** \<system\_error\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [\<system\_error\>](../standard-library/system-error.md)