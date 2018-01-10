---
title: dans (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.in
dev_langs: C++
helpviewer_keywords: in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37eaee8d796897b14d4780f0cf65e36908d7c66b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="in-c"></a>in (C++)
Indique qu’un paramètre est à passer à la procédure appelée à partir de la procédure appelante.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
[in]  
  
```  
  
## <a name="remarks"></a>Notes  
 Le **dans** attribut C++ a les mêmes fonctionnalités que le [dans](http://msdn.microsoft.com/library/windows/desktop/aa367051) attribut MIDL.  
  
## <a name="example"></a>Exemple  
 Consultez [pouvant être liés](../windows/bindable.md) pour obtenir un exemple montrant comment utiliser **dans**.  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Paramètre d’interface, méthode d’interface|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun.|  
|**Attributs non valides**|**retval**|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs de paramètre](../windows/parameter-attributes.md)   
 [Attributs de méthode](../windows/method-attributes.md)   
 [DefaultValue](../windows/defaultvalue.md)   
 [ID](../windows/id.md)   
 [out](../windows/out-cpp.md)   
