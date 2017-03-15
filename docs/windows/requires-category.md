---
title: "requires_category | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.requires_category"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "requires_category attribute"
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# requires_category
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

spécifie les catégories de composant requis de la classe cible.  
  
## Syntaxe  
  
```  
  
     [ requires_category(   
  requires_category  
) ]  
```  
  
#### Paramètres  
 *requires\_category*  
 L'ID de la catégorie obligatoire.  
  
## Notes  
 l'attribut de **requires\_category** C\+\+ spécifie les catégories de composants requises par la classe cible.  Pour plus d'informations, consultez [REQUIRED\_CATEGORY](../Topic/REQUIRED_CATEGORY.md).  
  
 Cet attribut requiert que [coclasse](../windows/coclass.md), [progid](../windows/progid.md), ou un attribut de [vi\_progid](../windows/vi-progid.md) \(ou un attribut différent qui implique un d'eux\) également être appliqués au même élément.  
  
## Exemple  
 Le code suivant requiert que l'objet implémentent la catégorie de contrôle.  
  
```  
// cpp_attr_ref_requires_category.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="MyLibrary")];  
  
[ coclass, requires_category("CATID_Control"),  
  uuid("1e1a2436-f3ea-4ff3-80bf-5409370e8144")]  
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
 [COM Attributes](../windows/com-attributes.md)   
 [implements\_category](../windows/implements-category.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)