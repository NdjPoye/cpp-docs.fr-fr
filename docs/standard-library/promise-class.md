---
title: "promise, classe | Microsoft Docs"
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
  - "future/std::promise"
dev_langs: 
  - "C++"
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# promise, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un *fournisseur asynchrone*.  
  
## Syntaxe  
  
```  
template<class Ty>  
class promise;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[promise::promise, constructeur](../Topic/promise::promise%20Constructor.md)|Construit un objet `promise`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[promise::get\_future, méthode](../Topic/promise::get_future%20Method.md)|Retourne un [futur](../standard-library/future-class.md) associé à cette promesse.|  
|[promise::set\_exception, méthode](../Topic/promise::set_exception%20Method.md)|Définit atomiquement le résultat de cette promesse pour désigner une exception.|  
|[promise::set\_exception\_at\_thread\_exit, méthode](../Topic/promise::set_exception_at_thread_exit%20Method.md)|Définit atomiquement le résultat de cette promesse pour afficher une exception, fournissant la notification seulement après que tous les objets du thread local aient été détruits \(généralement à la sortie du thread\).|  
|[promise::set\_value, méthode](../Topic/promise::set_value%20Method.md)|Définit atomiquement le résultat de cette promesse pour indiquer une valeur.|  
|[promise::set\_value\_at\_thread\_exit, méthode](../Topic/promise::set_value_at_thread_exit%20Method.md)|Définit atomiquement le résultat de cette promesse pour indiquer une valeur, fournissant la notification seulement après que tous les objets du thread local aient été détruits \(généralement à la sortie du thread\).|  
|[promise::swap, méthode](../Topic/promise::swap%20Method.md)|Échange *l'état asynchrone associé* de cet objet promesse avec celui d'un objet spécifié.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[promise::operator\=, opérateur](../Topic/promise::operator=%20Operator.md)|Attribution de l'état partagé de cet objet de promesse.|  
  
## Hiérarchie d'héritage  
 `promise`  
  
## Configuration requise  
 **En\-tête :** future  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)