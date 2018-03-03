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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b0e111103ecf42b44bd03b7b5ed154586676812
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrtrelease"></a>_com_ptr_t::Release
**Section spécifique à Microsoft**  
  
 Appelle le **version** fonction membre de **IUnknown** sur le pointeur d’interface encapsulé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
void Release( );  
  
```  
  
## <a name="remarks"></a>Notes  
 Appels `IUnknown::Release` sur le pointeur d’interface encapsulé, le déclenchement d’un `E_POINTER` erreur si ce pointeur d’interface est **NULL**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_ptr_t, classe](../cpp/com-ptr-t-class.md)