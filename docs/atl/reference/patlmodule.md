---
title: _pAtlModule | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATLBASE/_pAtlModule
- _pAtlModule
- ATL::_pAtlModule
- ATL._pAtlModule
dev_langs:
- C++
helpviewer_keywords:
- pAtlModule variable
- _pAtlModule variable
ms.assetid: 0ecde3a9-3f4d-4c7b-bb54-713ce05c4777
caps.latest.revision: 13
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
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: b20c5010616323eac9438223df64af9960192e2b
ms.lasthandoff: 02/24/2017

---
# <a name="patlmodule"></a>_pAtlModule
Une variable globale, le stockage d’un pointeur vers le module actuel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
__declspec(selectany) CAtlModule* _pAtlModule  
```  
  
## <a name="remarks"></a>Remarques  
 Méthodes sur cette variable globale peuvent être utilisés pour fournir les fonctionnalités que la classe (obsolète) [CComModule](../../atl/reference/ccommodule-class.md) fournis dans Visual C++ 6.0.  
  
## <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#97;](../../atl/codesnippet/cpp/patlmodule_1.cpp)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
## <a name="see-also"></a>Voir aussi  
 [Variables globales](../../atl/reference/atl-global-variables.md)




