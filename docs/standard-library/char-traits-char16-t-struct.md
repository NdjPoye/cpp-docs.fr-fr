---
title: char_traits&lt;char16_t&gt;, struct | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- char_traits<char16_t>
- string/std::char_traits<char16_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<char16_t> class
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
caps.latest.revision: 15
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
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: f1bd54744bcb80508b275f530c913ddafbd53c4f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/19/2017

---
# <a name="chartraitsltchar16tgt-struct"></a>char_traits&lt;char16_t&gt;, struct
Struct qui est une spécialisation du struct de modèle **char_traits\<CharType>** sur un élément de type `char16_t`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <>  
struct char_traits<char16_t>;
```  
  
## <a name="remarks"></a>Notes  
 La spécialisation permet au struct de tirer parti des fonctions de bibliothèque qui manipulent les objets du type `char16_t`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<string>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [\<string>](../standard-library/string.md)   
 [char_traits, struct](../standard-library/char-traits-struct.md)   
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)




