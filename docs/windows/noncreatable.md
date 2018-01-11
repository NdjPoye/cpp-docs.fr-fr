---
title: noncreatable | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.noncreatable
dev_langs: C++
helpviewer_keywords: noncreatable attribute
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb9f67b4efac28a1cacd6301c8ca849246f9a481
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="noncreatable"></a>noncreatable
Définit un objet qui ne peut pas être instancié par lui-même.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
[noncreatable]  
  
```  
  
## <a name="remarks"></a>Notes  
 Le **noncreatable** attribut C++ a les mêmes fonctionnalités que le [noncreatable](http://msdn.microsoft.com/library/windows/desktop/aa367118) attribut MIDL et est automatiquement transféré vers le texte généré. Fichier IDL par le compilateur.  
  
 Lorsque cet attribut est utilisé dans un projet qui utilise ATL, le comportement de l’attribut change. En plus du comportement ci-dessus, l’attribut injecte également le [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) (macro). Cette macro indique à ATL que l’objet ne peut pas être créé en externe.  
  
## <a name="example"></a>Exemple  
  
```  
// cpp_attr_ref_noncreatable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("11111111-1111-1111-1111-111111111111")]  
__interface A   
{  
};  
  
[coclass, uuid("11111111-1111-1111-1111-111111111112"), noncreatable]  
class CMyClass : public A   
{  
   HRESULT xx();  
};  
```  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**class**, `struct`|  
|**Renouvelable**|Non|  
|**Attributs requis**|**coclass**|  
|**Attributs non valides**|Aucun.|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs de classe](../windows/class-attributes.md)   
