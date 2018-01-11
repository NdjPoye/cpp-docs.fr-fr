---
title: retval | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.retval
dev_langs: C++
helpviewer_keywords: retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf7aa0cf8dd9767f603807ee18e23fe02d3446c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="retval"></a>retval
Désigne le paramètre qui reçoit la valeur de retour du membre.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
[retval]  
  
```  
  
## <a name="remarks"></a>Notes  
 Le **retval** attribut C++ a les mêmes fonctionnalités que le [retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) attribut MIDL.  
  
 **retval** doit apparaître sur le dernier argument dans la déclaration d’une fonction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple de [pouvant être liés](../windows/bindable.md) pour un exemple d’utilisation de **retval**.  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Paramètre d’interface, méthode d’interface|  
|**Renouvelable**|Non|  
|**Attributs requis**|**out**|  
|**Attributs non valides**|**in**|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs de paramètre](../windows/parameter-attributes.md)   
 [Attributs de méthode](../windows/method-attributes.md)   
