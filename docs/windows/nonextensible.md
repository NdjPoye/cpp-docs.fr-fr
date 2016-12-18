---
title: "nonextensible | Microsoft Docs"
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
  - "vc-attr.nonextensible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nonextensible attribute"
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# nonextensible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie que l'implémentation d' `IDispatch` inclut uniquement les propriétés et les méthodes figurant dans la description d'interface et ne peut pas être étendue avec les membres supplémentaires au moment de l'exécution.  
  
## Syntaxe  
  
```  
  
[nonextensible]  
  
```  
  
## Notes  
 L'attribut de **non extensible** C\+\+ a les mêmes fonctionnalités que l'attribut de [non extensible](http://msdn.microsoft.com/library/windows/desktop/aa367120) MIDL.  
  
 L'utilisation de **non extensible** requiert également l'attribut de [oleautomation](../windows/oleautomation.md) .  
  
## Exemple  
 Le code suivant présente une utilisation de l'attribut de **non extensible** :  
  
```  
// cpp_attr_ref_nonextensible.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export] typedef long HRESULT;  
  
[dual, nonextensible, ms_union, oleautomation,   
uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   HRESULT procedure (int i);   
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`interface`|  
|**reproductible**|Non|  
|**attributs requis**|**double** et **oleautomation**, ou **dispinterface**|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)