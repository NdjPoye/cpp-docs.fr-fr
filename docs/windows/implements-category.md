---
title: implements_category | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.implements_category
dev_langs: C++
helpviewer_keywords: implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6ab6206851385dcf7bf73cf56730093e7fc5c48f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="implementscategory"></a>implements_category
Spécifie les catégories de composant implémentés par la classe cible.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ implements_category(  
   implements_category="uuid"  
) ]  
```  
  
#### <a name="parameters"></a>Paramètres  
 **implements_category**  
 L’ID de la catégorie de mise en œuvre.  
  
## <a name="remarks"></a>Notes  
 Le **implements_category** attribut C++ Spécifie les catégories de composant implémentés par la classe cible. Cela en créant un mappage de catégorie et en ajoutant des entrées distinctes spécifiées par le **implements_category** attribut. Pour plus d’informations, consultez [quelles sont les catégories de composants et comment effectuer leur travail ?](http://msdn.microsoft.com/library/windows/desktop/ms694322).  
  
 Cet attribut exige que l’attribut [coclass](../windows/coclass.md), [progid](../windows/progid.md)ou [vi_progid](../windows/vi-progid.md) (ou un autre attribut qui implique l’un de ceux-ci) soit également appliqué au même élément. Si un attribut unique est utilisé, les deux autres sont appliqués automatiquement. Par exemple, si **progid** est appliqué, **vi_progid** et **coclass** sont également appliqués.  
  
## <a name="example"></a>Exemple  
 Le code suivant spécifie que l’objet suivant implémente la catégorie de contrôle.  
  
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
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**class**, `struct`|  
|**Renouvelable**|Oui|  
|**Attributs requis**|Une des valeurs suivantes : **coclasse**, **progid**, ou **vi_progid**|  
|**Attributs non valides**|Aucun.|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs COM](../windows/com-attributes.md)   
 [Attributs de classe](../windows/class-attributes.md)   
 [IMPLEMENTED_CATEGORY](../atl/reference/category-macros.md#implemented_category)   
 