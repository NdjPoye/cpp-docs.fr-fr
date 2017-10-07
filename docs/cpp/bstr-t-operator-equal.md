---
title: _bstr_t::operator = | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 445c18ece9b998d5cfa75a1c9fe5bde3b60b2e52
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtoperator-"></a>_bstr_t::operator =
**Section spécifique à Microsoft**  
  
 Assigne une nouvelle valeur à un objet `_bstr_t` existant.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      _bstr_t& operator=(  
   const _bstr_t& s1   
) throw ( );  
_bstr_t& operator=(  
   const char* s2   
);  
_bstr_t& operator=(  
   const wchar_t* s3   
);  
_bstr_t& operator=(  
   const _variant_t& var   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *s1*  
 Objet `_bstr_t` à assigner à un objet `_bstr_t` existant.  
  
 *s2*  
 Chaîne multioctets à assigner à un objet `_bstr_t` existant.  
  
 `s3`  
 Chaîne Unicode à assigner à un objet `_bstr_t` existant.  
  
 `var`  
 Objet `_variant_t` à assigner à un objet `_bstr_t` existant.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="example"></a>Exemple  
 Consultez [_bstr_t::Assign](../cpp/bstr-t-assign.md) pour obtenir un exemple d’utilisation de `operator=`.  
  
## <a name="see-also"></a>Voir aussi  
 [_bstr_t, classe](../cpp/bstr-t-class.md)
