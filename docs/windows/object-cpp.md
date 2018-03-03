---
title: objet (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.object
dev_langs:
- C++
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5714d7c3bd029c7b1df636044ed1968f53600848
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="object-c"></a>object (C++)
Identifie une interface personnalisée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
[object]  
  
```  
  
## <a name="remarks"></a>Notes  
 Lorsqu’il précède une définition d’interface, le **objet** attribut C++ provoque l’interface doit être placé dans le fichier .idl comme une interface personnalisée.  
  
 N’importe quelle interface marquée avec l’objet doit hériter de **IUnknown**. Cette condition est remplie si une des interfaces de base hérite de **IUnknown**. Si aucune interface de base ne hérite de **IUnknown**, le compilateur entraînera l’interface marquée avec **objet** dériver **IUnknown**.  
  
## <a name="example"></a>Exemple  
 Consultez [nonbrowsable](../windows/nonbrowsable.md) pour obtenir un exemple montrant comment utiliser **objet**.  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`interface`|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun.|  
|**Attributs non valides**|Aucun.|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs d’interface](../windows/interface-attributes.md)   
 [Double](../windows/dual.md)   
 [dispinterface](../windows/dispinterface.md)   
 [personnalisé](../windows/custom-cpp.md)   
 [__interface](../cpp/interface.md)   
