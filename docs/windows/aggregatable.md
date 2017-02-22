---
title: "aggregatable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.aggregatable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregatable attribute"
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# aggregatable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

indique que la classe prend en charge le regroupement.  
  
## Syntaxe  
  
```  
  
      [ aggregatable(   
   value  
) ]  
```  
  
#### Paramètres  
 *valeur* \(facultatif\)  
 un paramètre pour indiquer quand l'objet COM peut être regroupé :  
  
-   **jamais** l'objet COM ne peut pas être regroupé.  
  
-   **let** l'objet COM peut être créé directement ou il peut être regroupé.  Il s'agit de la valeur par défaut.  
  
-   **toujours** l'objet COM ne pouvez pas créer directement et ne peut être regroupé.  Lorsque vous appelez `CoCreateInstance` pour cet objet, vous devez spécifier l'interface d' **IUnknown** de l'objet agrégation \( **IUnknown**contrôle\).  
  
## Notes  
 L'attribut d' **aggregatable** C\+\+ a les mêmes fonctionnalités que l'attribut d' [aggregatable](http://msdn.microsoft.com/library/windows/desktop/aa366721) MIDL.  Cela signifie que le compilateur passe l'attribut d' **aggregatable** le fichier généré .idl.  
  
 Cet attribut requiert que [coclasse](../windows/coclass.md), [progid](../windows/progid.md), ou un attribut de [vi\_progid](../windows/vi-progid.md) \(ou un attribut différent qui implique un d'eux\) également être appliqués au même élément.  Si attribut unique en est utilisé, les deux autres sont automatiquement appliqués.  par exemple, si **progid** est appliqué, **vi\_progid** et **coclasse** sont également appliqués.  
  
 **Projets ATL**  
  
 si cet attribut est utilisé dans un projet qui utilise ATL, le comportement de l'attribut change.  Outre le comportement décrit précédemment, l'attribut ajoute également une des macros suivantes à la classe cible :  
  
|Valeur de paramètre|macro insérée|  
|-------------------------|-------------------|  
|**Jamais**|[DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)|  
|**Autorisé**|[DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md)|  
|**Toujours**|[DECLARE\_ONLY\_AGGREGATABLE](../Topic/DECLARE_ONLY_AGGREGATABLE.md)|  
  
## Exemple  
  
```  
// cpp_attr_ref_aggregatable.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="MyModule")];  
  
[ coclass, aggregatable(allowed),  
  uuid("1a8369cc-1c91-42c4-befa-5a5d8c9d2529")]  
class CMyClass {};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`|  
|**reproductible**|Non|  
|**attributs requis**|Un ou plusieurs des éléments suivants : **coclasse**, **progid**, ou **vi\_progid**.|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)