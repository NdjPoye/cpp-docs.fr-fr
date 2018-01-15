---
title: type_index, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: typeindex/std::type_index
dev_langs: C++
helpviewer_keywords: type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e27a626a7371c0358f05c49b33d0a9c1a019e72e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="typeindex-class"></a>type_index, classe
La classe `type_index` encapsule un pointeur dans la [classe type_info](../cpp/type-info-class.md) pour faciliter l’indexation par ces objets.  
  
class type_index { public: type_index(const type_info& tinfo); const char *name() const; size_t hash_code() const; bool operator==(const type_info& right) const; bool operator!=(const type_info& right) const; bool operator<(const type_info& right) const; bool operator\<=(const type_info& right) const; bool operator>(const type_info& right) const; bool operator>=(const type_info& right) const; };  
  
 Le constructeur initialise `ptr` à `&tinfo`.  
  
 `name` retourne `ptr->name()`.  
  
 `hash_code` retourne « `ptr->hash_code().` »  
  
 `operator==` retourne `*ptr == right.ptr`.  
  
 `operator!=` retourne `!(*this == right)`.  
  
 `operator<` retourne `*ptr->before(*right.ptr)`.  
  
 `operator<=` retourne « `!(right < *this).` »  
  
 `operator>` retourne `right < *this`.  
  
 `operator>=` retourne `!(*this < right)`.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de type au moment de l’exécution](../cpp/run-time-type-information.md)   
 [\<typeindex>](../standard-library/typeindex.md)



