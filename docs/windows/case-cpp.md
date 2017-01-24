---
title: "case (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.case"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "case attribute"
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# case (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

utilisé avec l'attribut de [switch\_type](../windows/switch-type.md) dans **union**.  
  
## Syntaxe  
  
```  
  
      [ case(  
   value  
) ]  
```  
  
#### Paramètres  
 *correspondante*  
 Une valeur d'entrée possible pour laquelle vous souhaitez fournir le traitement.  le type de **valeur** peut être l'un des types suivants :  
  
-   `int`  
  
-   `char`  
  
-   **boolean**  
  
-   `enum`  
  
 ou un identificateur de ce type.  
  
## Notes  
 L'attribut d' **événement** C\+\+ a les mêmes fonctionnalités que l'attribut d' **événement** MIDL.  Cet attribut est utilisé uniquement avec l'attribut de [switch\_type](../windows/switch-type.md) .  
  
## Exemple  
 Le code suivant illustre une utilisation de l'attribut d' **événement** :  
  
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
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|membre de **classe** ou d' `struct`|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)