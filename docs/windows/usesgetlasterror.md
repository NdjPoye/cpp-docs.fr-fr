---
title: usesgetlasterror | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05c74f1254230270654b3dc0b44f541e4fe9ef2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="usesgetlasterror"></a>usesgetlasterror
Indique à l’appelant que s’il existe une erreur lors de l’appel de cette fonction, puis l’appelant peut ensuite appeler `GetLastError` pour récupérer le code d’erreur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
[usesgetlasterror]  
  
```  
  
## <a name="remarks"></a>Notes  
 Le **usesgetlasterror** attribut C++ a les mêmes fonctionnalités que le [usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) attribut MIDL.  
  
## <a name="example"></a>Exemple  
 Consultez le [idl_module](../windows/idl-module.md) exemple pour obtenir un exemple montrant comment utiliser **usesgetlasterror**.  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**module** attribut|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun.|  
|**Attributs non valides**|Aucun.|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
