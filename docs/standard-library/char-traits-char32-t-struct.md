---
title: char_traits&lt;char32_t&gt;, struct | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iosfwd/std::char_traits<char_32t>
- char_traits<char32_t>
dev_langs: C++
helpviewer_keywords: char_traits<char32_t> class
ms.assetid: c0315466-45d0-4a99-b83e-3b1dbfbfbbc3
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a6b315da89f94da232f5d0ed44a9e3351f41824
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
