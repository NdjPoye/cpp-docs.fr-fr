---
title: _com_error::WCodeToHRESULT | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::WCodeToHRESULT
dev_langs:
- C++
helpviewer_keywords:
- WCodeToHRESULT method
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
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
ms.openlocfilehash: e5165f3bf0058d2c1f5ae4cb416fd6b26e0077d3
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT
**Section spécifique à Microsoft**  
  
 Mappe `wCode` 16 bits vers `HRESULT` 32 bits.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      static HRESULT WCodeToHRESULT(  
   WORD wCode   
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `wCode`  
 `wCode` 16 bits à mapper vers `HRESULT` 32 bits.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` 32 bits mappé à partir de `wCode` 16 bits.  
  
## <a name="remarks"></a>Remarques  
 Consultez le [WCode](../cpp/com-error-wcode.md) fonction membre.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error::WCode](../cpp/com-error-wcode.md)   
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error, classe](../cpp/com-error-class.md)
