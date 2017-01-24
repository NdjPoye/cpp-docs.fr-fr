---
title: "agr&#233;gats | Microsoft Docs"
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
  - "vc-attr.aggregates"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregates (attribut)"
  - "agrégation (C++)"
  - "objets d’agrégats (C++), aggregates (attribut)"
  - "agrégats (C++)"
ms.assetid: 67a084c9-941f-474b-a029-9c93b38ebe9a
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# agr&#233;gats
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique que l’objet agrège l’objet spécifié par le CLSID.  
  
## Syntaxe  
  
```  
  
[ aggregates(  
clsid,  
variable_name  
) ]  
  
```  
  
#### Paramètres  
 `clsid`  
 Spécifie le CLSID de l’objet qui peut être agrégé.  
  
 `variable_name`  
 Nom de la variable à insérer. Cette variable contient le **IUnknown** de l’objet en cours d’agrégation.  
  
## Notes  
 Quand il est appliqué à un objet, l’attribut C\+\+ **aggregates** implémente un wrapper externe pour l’objet en cours d’agrégation \(spécifié par `clsid`\).  
  
 Cet attribut exige que l’attribut [coclass](../windows/coclass.md), [progid](../windows/progid.md) ou [vi\_progid](../windows/vi-progid.md) \(ou un autre attribut qui implique l’un de ceux\-ci\) soit également appliqué au même élément. Si un attribut unique est utilisé, les deux autres sont appliqués automatiquement. Par exemple, si **progid** est appliqué, **vi\_progid** et **coclass** sont également appliqués.  
  
 **Projets ATL**  
  
 Si vous utilisez cet attribut dans un projet qui utilise ATL, le comportement de l’attribut change. Tout d’abord, l’entrée suivante est ajoutée au mappage COM de l’objet cible :  
  
```  
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(_m_spAttrXXX, clsid)  
```  
  
 Ensuite, la macro [DECLARE\_GET\_CONTROLLING\_UNKNOWN](../Topic/DECLARE_GET_CONTROLLING_UNKNOWN.md) est également ajoutée.  
  
## Exemple  
  
```  
// cpp_attr_ref_aggregates.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
// requires 'aggregatable.dll'  
// see aggregatable attribute to create 'aggregatable.dll'  
class DECLSPEC_UUID("1a8369cc-1c91-42c4-befa-5a5d8c9d2529") CMyClass;  
  
[module (name="MYObject")];  
[object, uuid("ab006d85-e754-47c5-9ef4-2744ff32a20c")]  
__interface IObject  
{  
};  
  
[ coclass, aggregates(__uuidof(CMyClass)),   
  uuid("91cb2c06-8931-432a-baac-206e55c4edfb")]  
struct CObject : IObject  
{  
   int i;  
};  
```  
  
## Configuration requise  
  
### Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**class**, `struct`|  
|**Renouvelable**|Oui|  
|**Attributs requis**|Un ou plusieurs des éléments suivants : **coclass**, **progid** ou **vi\_progid**.|  
|**Attributs non valides**|None|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Agrégation](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
 [Aggregatable](http://msdn.microsoft.com/library/windows/desktop/aa366721)   
 [COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)