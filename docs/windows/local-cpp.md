---
title: local (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.local
dev_langs: C++
helpviewer_keywords: local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 007d95d5db0785deae08744b46738d7188e4da70
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="local-c"></a>local (C++)
Lorsqu’il est utilisé dans l’en-tête de l’interface, vous permet d’utiliser le compilateur MIDL comme un générateur d’en-tête. Lorsqu’il est utilisé dans une fonction individuelle, désigne une procédure locale pour lequel aucun stub n’est générés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
[local]  
  
```  
  
## <a name="remarks"></a>Remarques  
 Le `local` attribut C++ a les mêmes fonctionnalités que le [local](http://msdn.microsoft.com/library/windows/desktop/aa367071) attribut MIDL.  
  
## <a name="example"></a>Exemple  
 Consultez [call_as](../windows/call-as.md) pour obtenir un exemple montrant comment utiliser `local`.  
  
## <a name="requirements"></a>Spécifications  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`interface`, méthode d’interface|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun|  
|**Attributs non valides**|**dispinterface**|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs d’interface](../windows/interface-attributes.md)   
 [Attributs de méthode](../windows/method-attributes.md)   
 [call_as](../windows/call-as.md)   
