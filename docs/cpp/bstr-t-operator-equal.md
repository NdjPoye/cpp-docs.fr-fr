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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed1de7a529d8c4c1b0d7ae8623d0f1c4a58b5075
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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