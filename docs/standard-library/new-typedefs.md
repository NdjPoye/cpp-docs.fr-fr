---
title: '&lt;new&gt;, typedefs | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
caps.latest.revision: 7
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: e23ea06002dc840997a0e7202f581cd81ef407c5
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt;, typedefs
||  
|-|  
|[new_handler](#new_handler)|  
  
##  <a name="new_handler"></a>  new_handler  
 Le type pointe vers une fonction pouvant être utilisée comme gestionnaire new.  
  
```
typedef void (*new_handler)();
```  
  
### <a name="remarks"></a>Remarques  
 Ce type de fonction de gestionnaire est appelé par **operatornew** ou `operator new[]` quand ils ne peuvent pas satisfaire à une demande de stockage supplémentaire.  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple utilisant `new_handler` comme valeur de retour, consultez [set_new_handler](../standard-library/new-functions.md#set_new_handler).  
  
## <a name="see-also"></a>Voir aussi  
 [\<new>](../standard-library/new.md)




