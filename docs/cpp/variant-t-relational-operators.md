---
title: "_variant_t, opérateurs relationnels | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
- _variant_t::operator!=
- _variant_t::operator==
dev_langs:
- C++
helpviewer_keywords:
- '!= operator'
- relational operators, _variant_t class
- operator!=, variant
- operator!=, relational operators
- operator !=, variant
- operator ==, variant
- operator==, variant
- operator !=, relational operators
- == operator, with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
caps.latest.revision: 6
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
ms.openlocfilehash: d8bcf9550e3e3f8af1836aa3f6e8747089837142
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="variantt-relational-operators"></a>_variant_t, opérateurs relationnels
**Section spécifique à Microsoft**  
  
 Comparez deux objets `_variant_t` pour déterminer leur égalité ou inégalité.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      bool operator==(  
   const VARIANT& varSrc   
) const;  
bool operator==(  
   const VARIANT* pSrc   
) const;  
bool operator!=(  
   const VARIANT& varSrc   
) const;  
bool operator!=(  
   const VARIANT* pSrc   
) const;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *varSrc*  
 A **VARIANT** à comparer avec la `_variant_t` objet.  
  
 `pSrc`  
 Pointeur vers le **VARIANT** à comparer avec la `_variant_t` objet.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne **true** si la comparaison est vérifiée, **false** si ce n’est pas le cas.  
  
## <a name="remarks"></a>Remarques  
 Compare un `_variant_t` de l’objet avec un **VARIANT**, le test d’égalité ou l’inégalité.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_variant_t, classe](../cpp/variant-t-class.md)
