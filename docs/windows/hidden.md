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
ms.openlocfilehash: a33faa8f0b21e26842f6ad6fc98c16228f8335ea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="hidden"></a>hidden
Indique que l’élément existe, mais ne doit pas être affiché dans un navigateur orienté utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
[hidden]  
  
```  
  
## <a name="remarks"></a>Remarques  
 Le **masqué** attribut C++ a les mêmes fonctionnalités que le [masqué](http://msdn.microsoft.com/library/windows/desktop/aa366861) attribut MIDL.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple de [pouvant être liés](../windows/bindable.md) pour obtenir un exemple montrant comment utiliser **masqué**.  
  
## <a name="requirements"></a>Spécifications  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`interface`, **classe**, `struct`, méthode, propriété|  
|**Renouvelable**|Non|  
|**Attributs requis**|**coclasse** (quand il s’applique à une **classe** ou un `struct`)|  
|**Attributs non valides**|None|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs d’interface](../windows/interface-attributes.md)   
 [Attributs de classe](../windows/class-attributes.md)   
 [Attributs de méthode](../windows/method-attributes.md)   
