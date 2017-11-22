---
title: hash, structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: typeindex/std::hash
dev_langs: C++
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: df52a07cde6f8a4f064e0d391589e9ce5794edfd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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


