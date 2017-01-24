---
title: "string (C++) | Microsoft Docs"
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
  - "vc-attr.string"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "string attribute"
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# string (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique qu' `char`unidimensionnel, `wchar_t`, le tableau de **byte** \(ou équivalent\) ou le pointeur à une telle tableau doivent être traités comme chaîne.  
  
## Syntaxe  
  
```  
  
[string]  
  
```  
  
## Notes  
 L'attribut de **chaîne** C\+\+ a les mêmes fonctionnalités que l'attribut de [chaîne](http://msdn.microsoft.com/library/windows/desktop/aa367270) MIDL.  
  
## Exemple  
 Le code suivant montre comment utiliser **chaîne** sur une interface et sur un typedef :  
  
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
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Tableau ou pointeur vers un tableau, paramètre de l'interface, méthode d'interface|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Array Attributes](../windows/array-attributes.md)   
 [export](../windows/export.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)