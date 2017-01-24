---
title: "bindable | Microsoft Docs"
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
  - "vc-attr.bindable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bindable attribute"
ms.assetid: a2360f92-927b-4af8-98cc-6eca7f4ec954
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# bindable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique que la propriété prend en charge la liaison des données.  
  
## Syntaxe  
  
```  
  
[bindable]  
  
```  
  
## Notes  
 L'attribut de **pouvant être liée** C\+\+ a les mêmes fonctionnalités que l'attribut de [pouvant être liée](http://msdn.microsoft.com/library/windows/desktop/aa366738) MIDL.  Vous pouvez l'utiliser sur les propriétés définies avec [propget](../windows/propget.md), [propput](../windows/propput.md), les attributs ou de [propputref](../windows/propputref.md) , ou vous pouvez définir manuellement une méthode pouvant être liée.  
  
 Les exemples suivants MFC illustrent l'utilisation de **pouvant être liée**:  
  
-   [Exemples : Contrôles ActiveX MFC](http://msdn.microsoft.com/fr-fr/a44adf86-0ba0-4504-bedb-512b6cba2e63)  
  
-   [CIRC, exemple : contrôle ActiveX](http://msdn.microsoft.com/fr-fr/9ba34d04-280e-49f4-90ae-41a6be44c95b)  
  
-   [TESTHELP, exemple : contrôle ActiveX contenant des info\-bulles et de l'aide](http://msdn.microsoft.com/fr-fr/d822861d-c6f0-4d0a-ad11-970eebb1e8cd)  
  
## Exemple  
 Le code suivant montre comment vous pouvez utiliser **pouvant être liée** sur une propriété :  
  
```  
// cpp_attr_ref_bindable.cpp  
// compile with: /LD  
#include <windows.h>  
[  
   uuid("479B29E3-9A2C-11D0-B696-00A0C903487A"),  
   dispinterface,  
   helpstring("property demo Interface")  
]  
__interface IPropDemo : IDispatch {  
  
   [propget, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);  
   [propput, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([in] long nSize);  
   [id(3), bindable, propget] HRESULT Object([out, retval] IDispatch **ppObj);  
   [id(3), bindable, propputref] HRESULT Object([in] IDispatch* pObj);     
   [id(-552), helpstring("method AboutBox")] HRESULT AboutBox();  
};  
  
[ module(name="PropDemoLib", uuid="479B29E2-9A2C-11D0-B696-00A0C903487A", version="1.0", helpstring="property demo") ];  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|méthode d'interface|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [defaultbind](../windows/defaultbind.md)   
 [displaybind](../windows/displaybind.md)   
 [immediatebind](../windows/immediatebind.md)   
 [requestedit](../windows/requestedit.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)