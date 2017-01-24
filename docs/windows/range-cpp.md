---
title: "range (C++) | Microsoft Docs"
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
  - "vc-attr.range"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "range attribute"
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# range (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie une plage de valeurs autorisées pour les arguments ou les champs dont les valeurs sont définies au moment de l'exécution.  
  
## Syntaxe  
  
```  
  
      [ range(  
   low,   
   high  
) ]  
```  
  
#### Paramètres  
 *bas*  
 La valeur de plage faible.  
  
 *haute*  
 la valeur de plage élevée.  
  
## Notes  
 L'attribut de **plage** C\+\+ a les mêmes fonctionnalités que l'attribut de [plage](http://msdn.microsoft.com/library/windows/desktop/aa367151) MIDL.  
  
## Exemple  
  
```  
// cpp_attr_ref_range.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
   HRESULT length_is1([in, range(0, 999)] long f, [in, length_is(f)] char array[10]);  
   HRESULT length_is2([in, range(-99, -1)] long f, [in, length_is("f"), size_is(10)] char *array);  
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|méthode d'interface, paramètre d'interface|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Data Member Attributes](../windows/data-member-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)