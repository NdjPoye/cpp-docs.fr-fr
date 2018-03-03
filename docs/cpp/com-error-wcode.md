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
- _com_error::WCode
dev_langs:
- C++
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 74f79491b9d4f88e19bcd0f7a20c94b26d0f7909
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
  
## <a name="remarks"></a>Notes  
 Le **WCode** méthode est utilisée pour annuler un mappage qui se produit dans le code de prise en charge COM. Le wrapper pour un **dispinterface** propriété ou une méthode appelle une routine d’assistance qui empaquette les arguments et appelle **IDispatch::Invoke**. Au retour, si une défaillance `HRESULT` de `DISP_E_EXCEPTION` est retourné, les informations d’erreur sont récupérées à partir de la **EXCEPINFO** structure passée au **IDispatch::Invoke**. Le code d’erreur peut être une valeur 16 bits stockée dans le `wCode` membre de la **EXCEPINFO** structure ou une valeur de 32 bits dans le **scode** membre de la **EXCEPINFO**structure. Si un `wCode` 16 bits est retourné, il doit d'abord être mappé à un `HRESULT` d'échec 32 bits.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error, classe](../cpp/com-error-class.md)