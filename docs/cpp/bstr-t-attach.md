---
title: _bstr_t::Attach | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
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
ms.openlocfilehash: 0541fadf224fd3f13377111d1bb1b7f5aca2f995
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtattach"></a>_bstr_t::Attach
**Section spécifique à Microsoft**  
  
 Lie un wrapper `_bstr_t` à un `BSTR`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      void Attach(  
   BSTR s  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *s*  
 `BSTR` à associer ou assigné à la variable `_bstr_t`.  
  
## <a name="remarks"></a>Remarques  
 Si `_bstr_t` a été précédemment attaché à un autre `BSTR`, `_bstr_t` nettoie la ressource `BSTR`, si aucune autre variable `_bstr_t` n'utilise `BSTR`.  
  
## <a name="example"></a>Exemple  
 Consultez [_bstr_t::Assign](../cpp/bstr-t-assign.md) pour un exemple utilisant **attacher**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_bstr_t, classe](../cpp/bstr-t-class.md)
