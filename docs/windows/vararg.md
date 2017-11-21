---
title: vararg | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.vararg
dev_langs: C++
helpviewer_keywords: vararg attribute
ms.assetid: 20fc3244-18e9-411c-990e-d5b4fa29a570
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 96689914ae299700f2640fa205cbad8887692454
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="vararg"></a>vararg
Spécifie que la fonction accepte un nombre variable d’arguments.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
[vararg]  
  
```  
  
## <a name="remarks"></a>Remarques  
 Le **vararg** attribut C++ a les mêmes fonctionnalités que le [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304) attribut MIDL.  
  
## <a name="example"></a>Exemple  
 Le code suivant illustre une utilisation de **vararg**:  
  
```  
// cpp_attr_ref_vararg.cpp  
// compile with: /LD  
#include "unknwn.h"  
#include "oaidl.h"  
[module(name="MyLibrary")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface X : public IUnknown   
{  
   [vararg] HRESULT Button([in, satype(VARIANT)]SAFEARRAY *psa);  
};  
```  
  
## <a name="requirements"></a>Spécifications  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Méthode d’interface|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun|  
|**Attributs non valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs de méthode](../windows/method-attributes.md)   
