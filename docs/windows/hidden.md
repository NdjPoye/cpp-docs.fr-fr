---
title: "masqué | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.hidden
dev_langs: C++
helpviewer_keywords: hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c038eb4869cb3191dd26b5c4ea8e1c6cc182e366
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="hidden"></a>hidden
Indique que l’élément existe, mais ne doit pas être affiché dans un navigateur orienté utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
[hidden]  
  
```  
  
## <a name="remarks"></a>Notes  
 Le **masqué** attribut C++ a les mêmes fonctionnalités que le [masqué](http://msdn.microsoft.com/library/windows/desktop/aa366861) attribut MIDL.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple de [pouvant être liés](../windows/bindable.md) pour obtenir un exemple montrant comment utiliser **masqué**.  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`interface`, **classe**, `struct`, méthode, propriété|  
|**Renouvelable**|Non|  
|**Attributs requis**|**coclasse** (quand il s’applique à une **classe** ou un `struct`)|  
|**Attributs non valides**|Aucun.|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs d’interface](../windows/interface-attributes.md)   
 [Attributs de classe](../windows/class-attributes.md)   
 [Attributs de méthode](../windows/method-attributes.md)   
