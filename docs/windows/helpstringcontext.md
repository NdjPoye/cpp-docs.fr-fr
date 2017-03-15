---
title: "helpstringcontext | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.helpstringcontext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "helpstringcontext attribute [C++]"
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# helpstringcontext
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie l'ID d'une rubrique d'aide dans un fichier de .hlp ou .chm.  
  
## Syntaxe  
  
```  
  
      [ helpstringcontext(  
   contextID  
) ]  
```  
  
#### Paramètres  
 `contextID`  
 un identificateur de contexte d'aide 32 bits dans le fichier d'aide.  
  
## Notes  
 L'attribut de **helpstringcontext** C\+\+ a les mêmes fonctionnalités que l'attribut de [helpstringcontext](http://msdn.microsoft.com/library/windows/desktop/aa366858) \).  
  
## Exemple  
  
```  
// cpp_attr_ref_helpstringcontext.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[   object,   
   helpstring("help string"),   
   helpstringcontext(1),   
   uuid="11111111-1111-1111-1111-111111111111"  
]  
__interface IMyI   
{  
   HRESULT xx();  
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `interface`, méthode d'interface|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [module](../windows/module-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)