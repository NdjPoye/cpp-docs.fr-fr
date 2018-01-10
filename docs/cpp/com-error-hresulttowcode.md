---
title: _com_error::HRESULTToWCode | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::HRESULTToWCode
dev_langs: C++
helpviewer_keywords: HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 14c4cdf85e67bdb0acd8dbadd178e3fbd2dbaf54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode
**Section spécifique à Microsoft**  
  
 Mappe les 32 bits `HRESULT` à 16 bits `wCode`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `hr`  
 32 bits `HRESULT` soit mappé à 16 bits `wCode`.  
  
## <a name="return-value"></a>Valeur de retour  
 16 bits `wCode` mappé à partir de 32 bits `HRESULT`.  
  
## <a name="remarks"></a>Notes  
 Consultez [_com_error::WCode](../cpp/com-error-wcode.md) pour plus d’informations.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error::WCode](../cpp/com-error-wcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error, classe](../cpp/com-error-class.md)