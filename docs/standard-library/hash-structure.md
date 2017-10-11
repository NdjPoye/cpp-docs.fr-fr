---
title: hash, structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- typeindex/std::hash
dev_langs:
- C++
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: c00698cac12ce0b12fb847e3ed97bf9c97f10895
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="hash-structure"></a>hash, structure
La classe de modèle définit sa méthode comme retournant `val.hash_code()`. La méthode définit une fonction de hachage qui sert à mapper les valeurs de type [type_index](../standard-library/type-index-class.md) à une distribution de valeurs d’index.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <>
struct hash<type_index>  
: public unary_function<type_index, size_t>
 { // hashes a typeinfo object
    size_t operator()(type_index val) const;

 };
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<typeindex>](../standard-library/typeindex.md)




