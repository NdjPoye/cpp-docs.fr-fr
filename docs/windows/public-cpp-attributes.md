---
title: public (attributs C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.public
dev_langs: C++
helpviewer_keywords: public attribute
ms.assetid: c42e1fd5-6cb1-48fe-8a03-95f2a2e0137c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c464f2fe2261018f2f18282b3cf3c2a62f31fde4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="public-c-attributes"></a>public (attributs C++)
Garantit qu’un typedef passera à la bibliothèque de types même s’il n’est pas référencé à partir du fichier .idl.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
[public]  
  
```  
  
## <a name="remarks"></a>Remarques  
 Le **public** attribut C++ a les mêmes fonctionnalités que le [public](http://msdn.microsoft.com/library/windows/desktop/aa367150) attribut MIDL.  
  
## <a name="example"></a>Exemple  
 Le code suivant montre comment utiliser le **public** attribut :  
  
```  
// cpp_attr_ref_public.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export, public] typedef long MEMBERID;  
  
[dispinterface, uuid(99999999-9999-9999-9999-000000000000)]  
__interface IFireTabCtrl : IDispatch  
{  
   [id(2)] long procedure ([in, optional] VARIANT i);  
};  
```  
  
## <a name="requirements"></a>Spécifications  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`typedef`|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun|  
|**Attributs non valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs Typedef, Enum, Union et Struct](../windows/typedef-enum-union-and-struct-attributes.md)   
