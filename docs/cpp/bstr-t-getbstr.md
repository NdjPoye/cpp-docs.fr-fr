---
title: _bstr_t::GetBSTR | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetBSTR
dev_langs:
- C++
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 376951862a82d6588221b592238c9346d31bad4d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtgetbstr"></a>_bstr_t::GetBSTR
**Section spécifique à Microsoft**  
  
 Pointe sur le début du `BSTR` encapsulé par l'objet `_bstr_t`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
BSTR& GetBSTR( );  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Début du `BSTR` encapsulé par l'objet `_bstr_t`.  
  
## <a name="remarks"></a>Remarques  
 `GetBSTR` affecte tous les objets `_bstr_t` qui partagent un `BSTR`. Plusieurs objets `_bstr_t` peuvent partager un `BSTR` en utilisant le constructeur de copie et `operator=`.  
  
## <a name="example"></a>Exemple  
 Consultez [_bstr_t::Assign](../cpp/bstr-t-assign.md) pour un exemple en utilisant `GetBSTR`.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_bstr_t, classe](../cpp/bstr-t-class.md)
