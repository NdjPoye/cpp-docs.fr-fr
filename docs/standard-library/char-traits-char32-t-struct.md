---
title: char_traits&lt;char32_t&gt;, struct | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- iosfwd/std::char_traits<char_32t>
- char_traits<char32_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<char32_t> class
ms.assetid: c0315466-45d0-4a99-b83e-3b1dbfbfbbc3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6d624cbeb797e5c81bb10d7ec8e532ce881cd700
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="chartraitsltchar32tgt-struct"></a>char_traits&lt;char32_t&gt;, struct
Struct qui est une spécialisation du struct de modèle **char_traits\<CharType>** sur un élément de type `char32_t`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <>  
struct char_traits<char32_t>;
```  
  
## <a name="remarks"></a>Notes  
 La spécialisation permet au struct de tirer parti des fonctions de bibliothèque qui manipulent les objets du type `char32_t`.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<string>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [\<string>](../standard-library/string.md)   
 [char_traits, struct](../standard-library/char-traits-struct.md)
