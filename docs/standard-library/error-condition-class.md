---
title: "error_condition, classe | Microsoft Docs"
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
  - "system_error/std::error_condition"
  - "std::error_condition"
  - "error_condition"
  - "std.error_condition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_condition (classe)"
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
caps.latest.revision: 16
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# error_condition, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente les codes d'erreur définis par l'utilisateur.  
  
## Syntaxe  
  
```  
class error_condition;  
```  
  
## Notes  
 Un objet de type `error_condition` stocke une valeur de code d'erreur et un pointeur vers un objet qui représente une [catégorie](../standard-library/error-category-class.md) de codes d'erreur utilisée pour les erreurs définies par l'utilisateur.  
  
### Constructeurs  
  
|||  
|-|-|  
|[error\_condition](../Topic/error_condition::error_condition.md)|Construit un objet de type `error_condition`.|  
  
### Typedef  
  
|||  
|-|-|  
|[type valeur](../Topic/error_condition::value_type.md)|Type qui représente la valeur du code d'erreur stocké.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[assign](../Topic/error_condition::assign.md)|Affecte une valeur et une catégorie de code d'erreur à une condition d'erreur.|  
|[Catégorie](../Topic/error_condition::category.md)|Retourne la catégorie d'erreur.|  
|[clear](../Topic/error_condition::clear.md)|Efface la valeur et la catégorie de code d'erreur.|  
|[message](../Topic/error_condition::message.md)|Retourne le nom du code d'erreur.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\=\=](../Topic/error_condition::operator==.md)|Teste si les deux objets `error_condition` sont égaux.|  
|[operator\!\=](../Topic/error_condition::operator!=.md)|Teste l'inégalité entre les objets `error_condition`.|  
|[.\<](../Topic/error_condition::operator%3C.md)|Vérifie si un objet `error_condition` est inférieur à l'objet `error_code` passé en vue de leur comparaison.|  
|[operator\=](../Topic/error_condition::operator=.md)|Assigne une nouvelle valeur d'énumération à l'objet `error_condition`.|  
|[operator bool](../Topic/error_condition::operator%20bool.md)|Convertit une variable de type `error_condition`.|  
  
## Configuration requise  
 **Header:** \<system\_error\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [error\_category, classe](../standard-library/error-category-class.md)   
 [\<system\_error\>](../standard-library/system-error.md)