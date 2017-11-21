---
title: "chaîne (C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.string
dev_langs: C++
helpviewer_keywords: string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0293785b9552b2e5696b9334e81aebf44c3bc4b7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="string-c"></a>string (C++)
Indique que la dimension `char`, `wchar_t`, **octets** (ou équivalent) tableau ou pointeur vers ce type de tableau doit être traité en tant que chaîne.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
[string]  
  
```  
  
## <a name="remarks"></a>Remarques  
 Le **chaîne** attribut C++ a les mêmes fonctionnalités que le [chaîne](http://msdn.microsoft.com/library/windows/desktop/aa367270) attribut MIDL.  
  
## <a name="example"></a>Exemple  
 Le code suivant montre comment utiliser **chaîne** sur une interface et un typedef :  
  
```  
// cpp_attr_ref_string.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export, string] typedef char a[21];  
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   [id(1)] HRESULT Method3([in, string] char *pC);  
};  
```  
  
## <a name="requirements"></a>Spécifications  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Tableau ou pointeur vers un tableau, le paramètre d’interface, la méthode d’interface|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun|  
|**Attributs non valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs de tableau](../windows/array-attributes.md)   
 [export](../windows/export.md)   
