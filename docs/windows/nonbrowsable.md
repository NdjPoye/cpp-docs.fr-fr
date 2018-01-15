---
title: nonbrowsable | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.nonbrowsable
dev_langs: C++
helpviewer_keywords: nonbrowsable attribute
ms.assetid: e71a98e7-4b65-454a-9829-342b9f2a84be
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 279d6e80fe100fbbd41e54c4a13640e3046cf73c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nonbrowsable"></a>nonbrowsable
Indique qu’un membre d’interface ne doit pas être affiché dans la fenêtre Propriétés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
[nonbrowsable]  
  
```  
  
## <a name="remarks"></a>Notes  
 Le **nonbrowsable** attribut C++ a les mêmes fonctionnalités que le [nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117) attribut MIDL.  
  
## <a name="example"></a>Exemple  
  
```  
// cpp_attr_ref_nonbrowsable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, helpstring("help string"), helpstringcontext(1),   
uuid="11111111-1111-1111-1111-111111111111"]   
__interface IMyI  
{  
   [nonbrowsable] HRESULT xx();  
};  
```  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Méthode d’interface|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun.|  
|**Attributs non valides**|Aucun.|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs de méthode](../windows/method-attributes.md)   
