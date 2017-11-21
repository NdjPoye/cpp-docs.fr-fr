---
title: cas (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.case
dev_langs: C++
helpviewer_keywords: case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1a3b76d56c6d1b78218d75ca596ae7311e13ac6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="case-c"></a>cas (C++)
Utilisé avec le [switch_type](../windows/switch-type.md) d’attribut dans un **union**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ case(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>Paramètres  
 *value*  
 Une valeur d’entrée possible pour lequel vous souhaitez fournir le traitement. Le type de **valeur** peut être un des types suivants :  
  
-   `int`  
  
-   `char`  
  
-   `boolean`  
  
-   `enum`  
  
 ou un identificateur d’un tel type.  
  
## <a name="remarks"></a>Remarques  
 Le **cas** attribut C++ a les mêmes fonctionnalités que le **cas** attribut MIDL. Cet attribut est utilisé uniquement avec les [switch_type](../windows/switch-type.md) attribut.  
  
## <a name="example"></a>Exemple  
 Le code suivant illustre une utilisation de la **cas** attribut :  
  
```  
// cpp_attr_ref_case.cpp  
// compile with: /LD  
#include <unknwn.h>  
[export]  
struct SizedValue2 {  
   [switch_type(char), switch_is(kind)] union {  
      [case(1), string]  
          wchar_t* wval;  
      [default, string]  
          char* val;  
   };  
    char kind;  
};  
[module(name="ATLFIRELib")];  
```  
  
## <a name="requirements"></a>Spécifications  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Membre d’un **classe** ou`struct`|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun|  
|**Attributs non valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union et Struct (attributs)](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributs de classe](../windows/class-attributes.md)   
