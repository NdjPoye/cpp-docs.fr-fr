---
title: "error_category, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::error_category"
  - "system_error/std::error_category"
  - "error_category"
  - "std.error_category"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_category (classe)"
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# error_category, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente la base abstraite, commune pour les objets qui décrit une catégorie de codes d’erreur.  
  
## Syntaxe  
  
```  
class error_category;  
```  
  
## Notes  
 Implémentent deux objets prédéfinis `error_category`: [generic\_category](../Topic/generic_category.md) et [system\_category](../Topic/system_category.md).  
  
### TypeDefs  
  
|||  
|-|-|  
|[value\_type](../Topic/error_category::value_type.md)|Type qui représente la valeur de code d’erreur stocké.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[default\_error\_condition](../Topic/error_category::default_error_condition.md)|Stocke la valeur de code d’erreur pour un objet de condition d’erreur.|  
|[equivalent](../Topic/error_category::equivalent.md)|Retourne une valeur qui spécifie si les objets d’erreur sont équivalents.|  
|[message](../Topic/error_category::message.md)|Retourne le nom de code d’erreur spécifié.|  
|[name](../Topic/error_category::name.md)|Retourne le nom de la catégorie.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\=\=](../Topic/error_category::operator==.md)|Teste l’égalité entre `error_category` objets.|  
|[\!\=, opérateur](../Topic/error_category::operator!=.md)|Vérifie l’inégalité entre `error_category` objets.|  
|[\< \(opérateur\)](../Topic/error_category::operator%3C.md)|Teste si le [error\_category](../standard-library/error-category-class.md) objet est inférieure à la `error_category` objet passé pour la comparaison.|  
  
## Configuration requise  
 **En\-tête :** \<system\_error\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<system\_error\>](../standard-library/system-error.md)