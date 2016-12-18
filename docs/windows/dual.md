---
title: "dual | Microsoft Docs"
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
  - "vc-attr.dual"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dual attribute"
ms.assetid: 5d4a9069-d819-42cd-ba56-bbcda17157d9
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# dual
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Place une interface dans le fichier .idl en tant qu'interface double.  
  
## Syntaxe  
  
```  
  
[dual]  
  
```  
  
## Notes  
 Lorsque l'attribut de **double** C\+\+ précède une interface, elle provoque l'interface à placer à l'intérieur de le bloc bibliothèque dans le fichier généré .idl.  
  
## Exemple  
 Le code suivant est un bloc d'attributs qui utilise **double** avant une définition d'interface :  
  
```  
// cpp_attr_ref_dual.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLibrary")];  
  
[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), dual]  
  
__interface IStatic : IDispatch   
{  
   HRESULT Func1(int i);  
   [   propget,   
      id(1),   
      bindable,   
      displaybind,   
      defaultbind,   
      requestedit  
   ]   
   HRESULT P1([out, retval] long *nSize);  
   [   propput,   
      id(1),   
      bindable,   
      displaybind,   
      defaultbind,   
      requestedit  
   ]   
   HRESULT P1([in] long nSize);      
};  
  
[cpp_quote("#include file.h")];  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`interface`|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|**dispinterface**|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Attributes by Usage](../windows/attributes-by-usage.md)   
 [custom](../windows/custom-cpp.md)   
 [dispinterface](../windows/dispinterface.md)   
 [object](../windows/object-cpp.md)   
 [\_\_interface](../cpp/interface.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)