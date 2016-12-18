---
title: "&lt;system_error&gt; | Microsoft Docs"
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
  - "std.<system_error>"
  - "std::<system_error>"
  - "<system_error>"
  - "system_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "system_error (en-tête)"
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;system_error&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Incluez l'en\-tête `<system_error>` pour définir la classe d'exception `system_error` et les modèles associés pour le traitement des erreurs système de bas niveau.  
  
## Syntaxe  
  
```  
#include <system_error>  
```  
  
### Objets  
  
|||  
|-|-|  
|[generic\_category](../Topic/generic_category.md)|Représente la catégorie d'erreur génériques.|  
|[system\_category](../Topic/system_category.md)|Représente la catégorie d'erreur causées par des dépassements de capacité de bas niveau système.|  
  
### Typedef  
  
|||  
|-|-|  
|[generic\_errno](../Topic/generic_errno.md)|Type qui représente l'énumération qui fournit les noms symboliques des macros de code d'erreur définis par Posix dans `<errno.h>`.|  
  
### Fonctions  
  
|||  
|-|-|  
|[make\_error\_code](../Topic/make_error_code.md)|Crée un objet `error_code`.|  
|[make\_error\_condition](../Topic/make_error_condition.md)|Crée un objet `error_condition`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\=\=](../Topic/operator==%20\(%3Csystem_error%3E\).md)|Teste si l'objet à gauche de l'opérateur est égal à l'objet du côté droit.|  
|[operator\!\=](../Topic/operator!=%20\(%3Csystem_error%3E\).md)|Teste si l'objet  à gauche de l'opérateur est non égal à l'objet du côté droit.|  
|[.\<](../Topic/operator%3C%20\(%3Csystem_error%3E\).md)|Vérifie si un objet est inférieur à l'objet passé en vue de leur comparaison.|  
  
### Énumérations  
  
|||  
|-|-|  
|[errc](../Topic/errc%20Enumeration.md)|Fournit des noms symboliques pour toutes les erreurs de code de macros définies par Posix dans `<errno.h>`.|  
  
### Classes et structs  
  
|||  
|-|-|  
|[error\_category](../standard-library/error-category-class.md)|Représente la base commune abstraite des objets qui décrivent une catégorie de codes d'erreur.|  
|[error\_code](../standard-library/error-code-class.md)|Représente les erreurs système de bas niveau qui sont spécifiques à l'implémentation.|  
|[error\_condition](../standard-library/error-condition-class.md)|Représente les codes d'erreur définis par l'utilisateur.|  
|[is\_error\_code\_enum](../standard-library/is-error-code-enum-class.md)|Représente un attribut de type qui détermine l'énumération [error\_code, classe](../standard-library/error-code-class.md).|  
|[is\_error\_condition\_enum](../standard-library/is-error-condition-enum-class.md)|Représente un attribut de type qui détermine l'énumération [error\_condition, classe](../standard-library/error-condition-class.md).|  
|[system\_error](../standard-library/system-error-class.md)|Représente la classe de base pour toutes les exceptions levées pour enregistrer un dépassement système de bas niveau.|  
  
## Configuration requise  
 **Header:** \<system\_error\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)