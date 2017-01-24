---
title: "implements_category | Microsoft Docs"
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
  - "vc-attr.implements_category"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "implements_category attribute"
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# implements_category
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

spécifie les catégories de composants implémentées par la classe cible.  
  
## Syntaxe  
  
```  
  
      [ implements_category(  
   implements_category="uuid"  
) ]  
```  
  
#### Paramètres  
 **implements\_category**  
 L'ID de la catégorie implémentée.  
  
## Notes  
 l'attribut d' **implements\_category** C\+\+ spécifie les catégories de composants implémentées par la classe cible.  Cela est fait en créant une carte de CATEGORY et en ajoutant des entrées distinctes spécifiées par l'attribut d' **implements\_category** .  Pour plus d'informations, consultez [Les sont des catégories de composants et la façon dont ils fonctionnent ?](http://msdn.microsoft.com/library/windows/desktop/ms694322).  
  
 Cet attribut requiert que [coclasse](../windows/coclass.md), [progid](../windows/progid.md), ou un attribut de [vi\_progid](../windows/vi-progid.md) \(ou un attribut différent qui implique un d'eux\) également être appliqués au même élément.  Si attribut unique en est utilisé, les deux autres sont automatiquement appliqués.  par exemple, si **progid** est appliqué, **vi\_progid** et **coclasse** sont également appliqués.  
  
## Exemple  
 Le code suivant spécifie que l'objet suivant implémente la catégorie de contrôle.  
  
```  
// cpp_attr_ref_implements_category.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="MyLib")];  
[ coclass, implements_category("CATID_Control"),  
  uuid("20a0d0cc-5172-40f5-99ae-5e032f3205ae")]  
class CMyClass {};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`|  
|**reproductible**|Oui|  
|**attributs requis**|L'une des opérations suivantes : **coclasse**, **progid**, ou **vi\_progid**|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [IMPLEMENTED\_CATEGORY](../Topic/IMPLEMENTED_CATEGORY.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)