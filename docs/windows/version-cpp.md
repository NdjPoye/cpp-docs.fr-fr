---
title: version (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.version
dev_langs: C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db6c31df932890799f68e2ae466b0a927f0f999f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="version-c"></a>version (C++)
Identifie une version particulière entre plusieurs versions d’une classe.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ version(  
   "version"  
) ]  
```  
  
#### <a name="parameters"></a>Paramètres  
 *version*  
 Le numéro de version de la coclasse. Si non spécifié, 1.0 sera placé dans le fichier .idl.  
  
## <a name="remarks"></a>Notes  
 Le **version** attribut C++ a les mêmes fonctionnalités que le [version](http://msdn.microsoft.com/library/windows/desktop/aa367306) attribut MIDL et est passée au fichier .idl généré.  
  
## <a name="example"></a>Exemple  
 Consultez le [pouvant être liés](../windows/bindable.md) exemple pour un exemple d’utilisation de **version**.  
  
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
 [Attributs du compilateur](../windows/compiler-attributes.md)   
 [Attributs de classe](../windows/class-attributes.md)   
