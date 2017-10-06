---
title: _com_ptr_t::Release | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
dev_langs:
- C++
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
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
ms.openlocfilehash: 6f3875a48977b047dfd8706369d448838626e5c6
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtrelease"></a>_com_ptr_t::Release
**Section spécifique à Microsoft**  
  
 Appelle le **version** fonction membre de **IUnknown** sur le pointeur d’interface encapsulé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
void Release( );  
  
```  
  
## <a name="remarks"></a>Remarques  
 Appels `IUnknown::Release` sur le pointeur d’interface encapsulé, le déclenchement d’un `E_POINTER` erreur si ce pointeur d’interface est **NULL**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_ptr_t, classe](../cpp/com-ptr-t-class.md)
