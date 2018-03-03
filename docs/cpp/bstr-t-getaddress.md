---
title: _bstr_t::GetAddress | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetAddress
dev_langs:
- C++
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1b2b348277f7d33a32c8d0e6ad1fc80d51ec68d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtgetaddress"></a>_bstr_t::GetAddress
**Section spécifique à Microsoft**  
  
 Libère toute chaîne existante et retourne l'adresse d'une chaîne nouvellement allouée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
BSTR* GetAddress( );  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Pointeur désignant le `BSTR` encapsulé par l'objet `_bstr_t`.  
  
## <a name="remarks"></a>Notes  
 `GetAddress` affecte tous les objets `_bstr_t` qui partagent un `BSTR`. Plusieurs objets `_bstr_t` peuvent partager un `BSTR` en utilisant le constructeur de copie et `operator=`.  
  
## <a name="example"></a>Exemple  
 Consultez [_bstr_t::Assign](../cpp/bstr-t-assign.md) pour un exemple utilisant `GetAddress`.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_bstr_t, classe](../cpp/bstr-t-class.md)