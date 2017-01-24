---
title: "iid_is | Microsoft Docs"
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
  - "vc-attr.iid_is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iid_is attribute"
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# iid_is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie l'IID de l'interface COM vers lequel un pointeur d'interface.  
  
## Syntaxe  
  
```  
  
      [ iid_is(  
   "expression"  
) ]  
```  
  
#### Paramètres  
 *expression*  
 L'expression de langage c qui spécifie un IID d'une interface COM indiquée par un pointeur d'interface.  
  
## Notes  
 L'attribut d' **iid\_is** C\+\+ a les mêmes fonctionnalités que l'attribut d' [iid\_is](http://msdn.microsoft.com/library/windows/desktop/aa367044) MIDL.  
  
## Exemple  
 Le code suivant illustre l'utilisation d' **iid\_is**:  
  
```  
// cpp_attr_ref_iid_is.cpp  
// compile with: /LD  
#include "wtypes.h"  
#include "unknwn.h"  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl : IDispatch  
{  
   [id(1)] HRESULT CreateInstance([in] REFIID riid,[out, iid_is("riid")]   
   IUnknown ** ppvObject);  
};  
  
[module(name="ATLFIRELib")];  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Paramètre d'interface, une donnée membre|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)