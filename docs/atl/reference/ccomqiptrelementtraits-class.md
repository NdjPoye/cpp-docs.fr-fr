---
title: Classe de CComQIPtrElementTraits | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
dev_langs: C++
helpviewer_keywords: CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 30d4e73f3c1e4ad75b8b33442be4e64af1a11207
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomqiptrelementtraits-class"></a>Classe de CComQIPtrElementTraits
Cette classe fournit des méthodes, les fonctions statiques et typedefs utiles lors de la création de collections de pointeurs d’interface COM.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<typename I, const IID* piid=& __uuidof(I)>  
class CComQIPtrElementTraits : 
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```  
  
#### <a name="parameters"></a>Paramètres  
 `I`  
 Une interface COM en spécifiant le type de pointeur à stocker.  
  
 `piid`  
 Un pointeur vers l’IID de `I`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|Le type de données à utiliser pour l’ajout d’éléments à l’objet de classe de collection.|  
  
## <a name="remarks"></a>Notes  
 Cette classe est dérivée de méthodes et fournit un typedef utile lors de la création d’une classe de collection de [CComQIPtr](../../atl/reference/ccomqiptr-class.md) objets de pointeur d’interface COM. Cette classe est utilisée par les deux le [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) et [CInterfaceList](../../atl/reference/cinterfacelist-class.md) classes.  
  
 Pour plus d’informations, consultez [Classes de Collection ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CComQIPtrElementTraits`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlcoll.h  
  
##  <a name="inargtype"></a>CComQIPtrElementTraits::INARGTYPE  
 Le type de données à utiliser pour l’ajout d’éléments à l’objet de classe de collection.  
  
```
typedef I* INARGTYPE;
```  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
