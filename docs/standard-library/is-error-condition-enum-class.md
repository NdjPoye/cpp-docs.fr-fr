---
title: is_error_condition_enum, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- system_error/std::is_error_condition_enum
dev_langs:
- C++
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4f92a07a904ae80fb56e2cf21114bb79506dfa11
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="iserrorconditionenum-class"></a>is_error_condition_enum, classe
Représente un prédicat de type qui teste l’énumération [error_condition](../standard-library/error-condition-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <_Enum>
class is_error_condition_enum;
```  
  
## <a name="remarks"></a>Notes  
 Une instance de ce [prédicat de type](../standard-library/type-traits.md) contient la valeur true si le type `_Enum` est une valeur d’énumération adaptée au stockage dans un objet de type `error_condition`.  
  
 Il est permis d’ajouter des spécialisations à ce type pour les types définis par l’utilisateur.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<system_error>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)   
 [<system_error>](../standard-library/system-error.md)



