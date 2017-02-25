---
title: "switch_type | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.switch_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "switch_type attribute"
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# switch_type
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Identifie le type de la variable utilisée comme une union discriminante.  
  
## Syntaxe  
  
```  
  
[switch_type(  
type  
}]  
  
```  
  
#### Paramètres  
 `type`  
 Le type de commutateur, peut être un entier, un caractère, un type Boolean, ou d'énumération.  
  
## Notes  
 L'attribut de **switch\_type** C\+\+ a les mêmes fonctionnalités que l'attribut de [switch\_type](http://msdn.microsoft.com/library/windows/desktop/aa367276) MIDL.  
  
 Les attributs C\+\+ ne prennent pas en charge [unions encapsulés](http://msdn.microsoft.com/library/windows/desktop/aa366811).  [Union de Nonencapsulated](http://msdn.microsoft.com/library/windows/desktop/aa367119) sont pris en charge uniquement sous la forme suivante :  
  
```  
// cpp_attr_ref_switch_type.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLibrary")];  
[ export ]  
struct SizedValue2 {  
   [switch_type("char"), switch_is(kind)] union {  
      [case(1), string]  
         wchar_t* wval;  
      [default, string]  
         char* val;  
   };  
   char kind;  
};  
```  
  
## Exemple  
 Consultez l'exemple d' [événement](../windows/case-cpp.md) pour un usage d'exemple de **switch\_type**.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`typedef`|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [export](../windows/export.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)