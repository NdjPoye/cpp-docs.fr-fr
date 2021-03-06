---
title: source (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.source
dev_langs:
- C++
helpviewer_keywords:
- source attribute
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11ee58fb2d500a7194fb08ee18b1af5cc7897830
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="source-c"></a>source (C++)
Sur une classe, spécifie les interfaces de source de l’objet COM pour les points de connexion. Sur une propriété ou une méthode, indique que le membre retourne un objet ou un VARIANT et qui est une source d’événements.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ source(  
   interfaces  
) ]  
```  
  
#### <a name="parameters"></a>Paramètres  
 `interfaces`  
 Une ou plusieurs interfaces que vous spécifiez lorsque vous appliquez la source de l’attribut à une classe. Ce paramètre n’est pas utilisé lors de la source est appliquée à une propriété ou méthode.  
  
## <a name="remarks"></a>Notes  
 Le **source** attribut C++ a les mêmes fonctionnalités que le [source](http://msdn.microsoft.com/library/windows/desktop/aa367166) attribut MIDL.  
  
 Vous pouvez utiliser la [par défaut](../windows/default-cpp.md) attribut pour spécifier l’interface source par défaut pour un objet.  
  
## <a name="example"></a>Exemple  
  
```  
// cpp_attr_ref_source.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid(11111111-1111-1111-1111-111111111111)]  
__interface b  
{  
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]  
   HRESULT get_I([out, retval]long *i);  
};  
  
[object, uuid(11111111-1111-1111-1111-111111111131)]  
__interface c  
{  
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]   
   HRESULT et_I([out, retval]long *i);  
};  
  
[coclass, default(c), uuid(11111111-1111-1111-1111-111111111132)]  
class N : public b  
{  
};  
  
[coclass, source(c), default(b, c), uuid(11111111-1111-1111-1111-111111111133)]  
class NN : public b  
{  
};  
```  
  
## <a name="requirements"></a>Spécifications  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`, `interface`|  
|**Renouvelable**|Non|  
|**Attributs requis**|**coclasse** (lorsqu’il est appliqué à la classe ou struct)|  
|**Attributs non valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs de classe](../windows/class-attributes.md)   
 [Attributs de méthode](../windows/method-attributes.md)   
 [coclass](../windows/coclass.md)   
