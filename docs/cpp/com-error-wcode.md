---
title: _com_error::WCode | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error.WCode
- _com_error::WCode
- WCode
dev_langs:
- C++
helpviewer_keywords:
- WCode method
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
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
ms.openlocfilehash: 15c0d860a5faffc160def725630fbbb1d84d8ed8
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorwcode"></a>_com_error::WCode
**Section spécifique à Microsoft**  
  
 Récupère le code d'erreur 16 bits mappé dans le `HRESULT` encapsulé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
WORD WCode ( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Si le `HRESULT` se trouve dans la plage 0 x 80040200 à 0x8004FFFF, la **WCode** méthode retourne la `HRESULT` moins 0 x 80040200 ; sinon, elle retourne zéro.  
  
## <a name="remarks"></a>Remarques  
 Le **WCode** méthode est utilisée pour annuler un mappage qui se produit dans le code de prise en charge COM. Le wrapper pour un **dispinterface** propriété ou une méthode appelle une routine d’assistance qui empaquette les arguments et appelle **IDispatch::Invoke**. Au retour, si une défaillance `HRESULT` de `DISP_E_EXCEPTION` est retourné, les informations d’erreur sont récupérées à partir de la **EXCEPINFO** structure passée au **IDispatch::Invoke**. Le code d’erreur peut être une valeur 16 bits stockée dans le `wCode` membre de la **EXCEPINFO** structure ou une valeur de 32 bits dans le **scode** membre de la **EXCEPINFO**structure. Si un `wCode` 16 bits est retourné, il doit d'abord être mappé à un `HRESULT` d'échec 32 bits.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error, classe](../cpp/com-error-class.md)
