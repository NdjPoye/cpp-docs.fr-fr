---
title: char_traits&lt;wchar_t&gt;, struct | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
dev_langs: C++
helpviewer_keywords: char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea9e39defefae6133f73262c90f0da9db3ea2edf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="chartraitsltwchartgt-struct"></a>char_traits&lt;wchar_t&gt;, struct
Classe qui est une spécialisation du struct de modèle **char_traits\<CharType>** sur un élément de type `wchar_t`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <>  
struct char_traits<wchar_t>;
```  
  
## <a name="remarks"></a>Notes  
 La spécialisation permet au struct de tirer parti des fonctions de bibliothèque qui manipulent les objets du type `wchar_t`.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<string>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [char_traits, struct](../standard-library/char-traits-struct.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)



