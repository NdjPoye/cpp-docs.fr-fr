---
title: type_index, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- typeindex/std::type_index
dev_langs:
- C++
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: e00ba54975dfac0439509e63606e9992d86c9522
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

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




