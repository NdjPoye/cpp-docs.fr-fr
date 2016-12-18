---
title: "error_code, classe | Microsoft Docs"
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
  - "error_code"
  - "std.error_code"
  - "std::error_code"
  - "system_error/std::error_code"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_code (classe)"
ms.assetid: c09b4a96-cb14-4281-a319-63543f9b2b4a
caps.latest.revision: 17
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# error_code, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente les erreurs système de bas niveau qui sont à l'implémentation.  
  
## Syntaxe  
  
```  
class error_code;  
```  
  
## Notes  
 Objet de la classe d'`error_code` de type stocke une valeur de code d'erreur et un pointeur vers un objet qui représente [catégorie](../standard-library/error-category-class.md) des codes d'erreur qui décrivent les erreurs système de bas niveau stockées.  
  
### Constructeurs  
  
|||  
|-|-|  
|[error\_code](../Topic/error_code::error_code.md)|Construit un objet de type `error_code`.|  
  
### Typedef  
  
|||  
|-|-|  
|[type valeur](../Topic/error_code::value_type.md)|Type qui représente la valeur stockée code d'erreur.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[assign](../Topic/error_code::assign.md)|Affecte une valeur et une catégorie de code d'erreur au code d'erreur.|  
|[Catégorie](../Topic/error_code::category.md)|Retourne la catégorie d'erreur.|  
|[clear](../Topic/error_code::clear.md)|Efface la valeur et la catégorie d'erreur.|  
|[default\_error\_condition](../Topic/error_code::default_error_condition.md)|Retourne la condition d'erreur par défaut.|  
|[message](../Topic/error_code::message.md)|Retourne le nom du code d'erreur.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\=\=](../Topic/error_code::operator==.md)|Teste l'égalité entre des objets d'`error_code`.|  
|[operator\!\=](../Topic/error_code::operator!=.md)|Teste l'inégalité entre des objets d'`error_code`.|  
|[.\<](../Topic/error_code::operator%3C.md)|Teste si l'objet d'`error_code` est inférieur à l'objet d'`error_code` passé pour la comparaison.|  
|[operator\=](../Topic/error_code::operator=.md)|Affecte une nouvelle valeur d'énumération de l'objet d'`error_code`.|  
|[bool d'opérateur](../Topic/error_code::operator%20bool.md)|Convertit une variable de type `error_code`.|  
  
## Configuration requise  
 **Header:** \<system\_error\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [error\_category, classe](../standard-library/error-category-class.md)   
 [\<system\_error\>](../standard-library/system-error.md)