---
title: Virtual (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- virtual_cpp
- virtual
dev_langs:
- C++
helpviewer_keywords:
- virtual base classes [C++], declaring
- base classes [C++], virtual
- virtual functions [C++], declaring
- virtual keyword [C++]
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 851f911dd7c49df1d685afe63ef5134cf0d5f175
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="virtual-c"></a>virtual (C++)
Le mot clé `virtual` déclare une fonction virtuelle ou une classe de base virtuelle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
virtual [type-specifiers] member-function-declarator  
virtual [access-specifier] base-class-name  
```  
  
#### <a name="parameters"></a>Paramètres  
 `type-specifiers`  
 Spécifie le type de retour de la fonction membre virtuelle.  
  
 `member-function-declarator`  
 Déclare une fonction membre.  
  
 `access-specifier`  
 Définit le niveau d'accès à la classe de base, `public`, `protected` ou `private`. Peut apparaître avant ou après le mot clé `virtual`.  
  
 `base-class-name`  
 Identifie un type de classe déclaré précédemment.  
  
## <a name="remarks"></a>Remarques  
 Consultez [fonctions virtuelles](../cpp/virtual-functions.md) pour plus d’informations.  
  
 Consultez également les mots clés suivants : [classe](../cpp/class-cpp.md), [privé](../cpp/private-cpp.md), [public](../cpp/public-cpp.md), et [protégé](../cpp/protected-cpp.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)
