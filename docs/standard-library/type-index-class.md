---
title: "type_index, classe | Microsoft Docs"
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
  - "typeindex/std::type_index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "type_index (classe)"
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
caps.latest.revision: 14
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# type_index, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe d'`type_index` encapsule un pointeur vers [type\_info, classe](../cpp/type-info-class.md) pour l'indexation par de ces objets.  
  
```  
class type_index {  
public:  
    type_index(const type_info& tinfo);  
    const char *name() const;  
    size_t hash_code() const;  
    bool operator==(const type_info& right) const;  
    bool operator!=(const type_info& right) const;  
    bool operator<(const type_info& right) const;  
    bool operator<=(const type_info& right) const;  
    bool operator>(const type_info& right) const;  
    bool operator>=(const type_info& right) const;  
};  
```  
  
 Le constructeur initialise `ptr` à `&tinfo`.  
  
 `name` retourne `ptr->name()`.  
  
 `hash_code` retourne `ptr->hash_code().`  
  
 `operator==` retourne `*ptr == right.ptr`.  
  
 `operator!=` retourne `!(*this == right)`.  
  
 `operator<` retourne `*ptr->before(*right.ptr)`.  
  
 `operator<=` retourne `!(right < *this).`  
  
 retourne `right < *this`d'`operator>`.  
  
 `operator>=` retourne `!(*this < right)`.  
  
## Voir aussi  
 [Informations de type au moment de l'exécution](../cpp/run-time-type-information.md)   
 [\<typeindex\>](../standard-library/typeindex.md)